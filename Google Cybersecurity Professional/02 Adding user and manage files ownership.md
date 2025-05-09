___
**About**: In this lab we'll be working with users commands: Create user, create groups, appending groups and after that, deleting them all as we don't need them.

**Scenario**: In your organization, a new employee started working with the username `researcher9` that will work with a specific project and your job is to add a new user for them, give access to the specified file and manage their access during their time at the organization.
After that, we'll also how to add a user to secondary groups when this employee changed his role a couple of months later at the organization and his deletion after that, when he left the company an year later.

**Creating new user**:
	
When creating a new user we use the command `useradd` followed by the username you want to register. After creating the user, add it to the `research_team` system group so he can have access to all of the groups files using the command `usermod`:

![creating user and adding to a group](images/2_1_create_and_modify_user.png)


**Changing file's ownership**:
	
As said about the employee, he'll be handling with a special project so he needs access to the file `project_r.txt`, which is only accessible by it's owner:

![changing_ownership](images/2_2_changing_ownership.png)

**Adding to secondary group**:
	
When adding primary and secondary groups(s) pay attention on the option:
- -g: for primary groups;
- -G: for secondary groups;
  
![adding secondary group](images/2_3_add_secondary_group.png)

**Deleting user**:
	
With the command `userdel` we can delete the user easily, but attention with the output because when a user is created it's also create a group with the same name, so when deleting the user it's also necessary to delete it's group with the command `groupdel`.

![Deleting user and it's group](images/2_4_deleting_user_and_group.png)
