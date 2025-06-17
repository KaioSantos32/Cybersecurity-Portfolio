___

**Scenario**: You're a security analyst who must monitor traffic on your employer's network and you're required to configure Suricata and use it to trigger alerts;

# 1 Using a custom rule
	
For this exercise you'll be using the following custom rule:
```
alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)
```

Rules (or signatures) are divided in 3 components: **action**, **header** and **rule options**.

## Action
	
It's the first part of the signature and it dictates what to do if the conditions are met.
There are some actions available to use: **alert**, **drop**, **pass** and **reject**.

**Alert**: The alert action instructs to alert on selected network traffic. The  IDS will inspect the packets and ==send an alert when the packet matches== the case written;
	
**Drop**: The drop action also generates an alert, but the main action it takes is to drop the network (==only works on IPS mode==);
	
**Pass**: ==Allows the traffic to pass through==. This action can be used to override other rules. An ==exception to a Drop rule== can be ==made using the Pass rule== by, for example, defining a specific IP address;
	
**Reject**: ==Blocks the traffic to pass==. It ==sends a TCP reset packet== and Suricata will drop the matching packet. (The ==reset packet tells computers to stop sending messages to each other==);

## Header
	
The second section is the header. where is defined the signature's network traffic that can includes protocols, source and destinations IP addresses and ports, and traffic direction.
Right after the action comes the protocol field, in our case, *http*. 
The parameters it receives are `$HOME_NET any -> $EXTERNAL_NET any`. The arrow indicates the direction of traffic that in this case means that the traffic is going to the external network from our home network (the `$HOME_NET` is a Suricata variable in `suricata.yaml`, it represents the home network). and the work `any` means that we don't want to catch a specific port, we want all.

## Rule options
	
This part is where you customize the signature. Configuring rule options helps narrow down network traffic to find exactly what you're looking for. Rule options are typically in parentheses and separated by semicolons.

The rule options of our custom rule is: 
`(msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)`

**msg**: Is the alert text. In this case the alert will print "GET on wire" when triggered;
	
**flow:established,to_server**: This part determines that the packets from the client to the server should be matched (by server it means the other device, the one responding with the SYN-ACK packet);
	
**content:"GET**: Tells to Suricata looks for the word "GET" in the content of the `http.method` portion;
	
**sid:12345**:is the signature ID, a unique numerical vale that identifies the rule;
	
**rev:3**: This indicates the signature's revision number, basically tells the "version" of the rule.

## Gathering all
	
Now to summarize:
```
This rule triggers an alert whenever Suricata observers a "GET" as the HTTP method in an HTTP packet coming from the home network and going to the external network.
```

## 2 Examining the .pcap file
	
To examine the file we use the following code after we create the file "custom.rule" with our rule in it:
`sudo suricata -r sample.pcap -S custom.rules -k none`

**-r**: let us specify an input file to mimic the network traffic;
**-S**: let us define the rules used;
**-k**: disable all checksum checks (checksum is a way to see if the packet has been modified in transit, and since we are using a sample, it's not necessary to check that)

After running the command, we get four new files:
![[11_1_files_after_suricata_analysis.png]]

Taking a look at the `fast.log`:
![[11_2_fast_log.png]]

With this result we can see that our custom rule worked and were triggered twice. We can see the rule ID `12345` and the message `GET on wire`.

# 3 Examining the eve.json file
	
To properly understand this file we can't use the `cat` command since it will show us a raw json with the information, totally unpractical.
Instead of `cat` we use `jq .` and in the end `| less` to show us in a readable form, like this:
![[11_3_eve_json.png]]

**Note**: Suricata export the files on folder located at `/var/log/suricata/` (the default location at least).