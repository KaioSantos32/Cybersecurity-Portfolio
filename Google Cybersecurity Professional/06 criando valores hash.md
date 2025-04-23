**Scenario**: 
	In this scenario, we need to investigate whether two files are identical or different.
	Here’s how you'll do this task: **First**, you’ll display the contents of two files and create hashes for each file. **Next**, you’ll examine the hashes and compare them.

# 1. Creating hash from files
	
First we need to check the existing files: "file1.txt" and "file2.txt".
![[images/6_1_showing_hashed_files.png]]

We now need to create a hash for these 2 files using `sha256sum`:
![[images/6_2_hashed_files.png]]

# 2. Comparing hashes
	
Now we'll compare the two hashes of files, but for that we need to store the hash created by the previous step into another file that we'll name "file1hash" and "file2hash":

![[images/6_3_storing_hashes.png]]

Now that we have the 2 hashes done, we can compare them with the command `cmp`.

![[images/6_4_comparing_hash.png]]