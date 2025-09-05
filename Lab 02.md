# Lab 02
- Name: Yazmin Robaina
- Email: robaina.3@wright.edu

//path to private key /////////////////////
//ssh command ///////////////////////////


## Part 2 - Bits of permissions
1) chmod u+r bubbles.txt
- meaning: The command "chmod u+r bubbles.txt" changes the level of interaction that the user has with the file, the u+r makes it so the user can read the bubbles.txt file. It does not affect anyone else but that user.
- Assessment: Pretty safe command giving the user the ability to read the bubble.txt file.without the file being overly exposed. But the user might need the ability to edit it later on, or what not.

2) chmod u=rw,g-w,o-x banana.cabana
- meaning: The command "chmod u=rw,g-w,o-x banana.cabana" gives the user of the file  permission to read and write. It removes the permission from g (group), the group cannot write in the banana file, only view it. Everyone else cannot run the file as  program.
- assessment: This is a good command that gives clear boundaries. Which makes it so the owner of the file can read + edit. While stopping others in the group from editing it giving file good security.

3) chmod a=w snow.md
- meaning: changes modify permissions for snow.md, to allow "a"(all users) to only write (w) on the mark down file.
- assessment: Not good command because it doesn't make sense to give all users just the ability to write, without the ability to read it. It doesn't realy make sense.

4) chmod 751 program
- meaning: The command changes the permission of the owner/user (7) which is the first digit, making it so they can read,write and execute the file. Then the second digit (5) makes the group just read and execute. And (1)  anyone else just able to execute.
- assessment: This seems like a good and safe permission set up. It allows the owner to r,w,and x. Makes the group just r and x without the ability to make unauthorized changes. And leaving anyone else with just the ability to run the program.

5) chmod -R ug+w share
- meaning: Command changes the ability to the (R) folder and everything inside, for the (u) user and (g) group plus the permission to (+w) write. Giving the owner and group permission to edit. With ability that shares that specifc directory and whatever is inside .
- Assessment: This seems like a safe command for group situations, it makes the owner and group share and modify, within that directory, assuming that there are non-sensitive files inside that shouldn't be edited .

## Part 3 - Regular bob
1) Create new User:
- I created a new user 'sudo adduser yazminrobaina'. Which created a new user with its personal home directory and login.
2) Path to new user’s home directory:
- I checked the new users directory by '/home/yazrobiana' and then I checked the list by ls/home and my new user was there.
3) Evaluate if ubuntu can add files to new user’s home directory:
-  As ubuntu i tried to create a file and couldn't write using 'touch myfile.txt' and permission was denied.
4) Command to switch to new user:
- I used command 'su - yazrobaina' which switched me from ubuntu to yazrobaina directory. i confirmed it with 'whoami' command. and output was yazrobaina user.
5) Command(s) to go to new user’s home directory: 
- I used 'pwd' command and saw I was still in yazrobaina directory, the output was '/home/yazrobaina' .
6) Command to return to ubuntu user:
-  I tried to see if yazrobaina could add files to ubuntu's home directory with command '/home/ubuntu/tester.txt', and i was denied because the yazrobaina is private directory and create files on ubuntu's end.
 7) Command to return to ubuntu home directory:
- Since I am in yazrobaina directory, I used 'exit' command to exit that user and it automatically puts me in ubuntu, and i used command 'whoami' to confirm. the output was 'ubuntu'
 8)  Command to return to ubuntu home directory: 
 - I used change directory command to home using 'cd~' and the output said /home/ubuntu .

## Part 4 Make Squad!
1) Command(s) to create group named squad and add members:
- I used the command 'sudo addgroup squad' the group is called squad that will have shared access to share folders allowed.
2) Command(s) to add ubuntu & user to group squad:
-  to add both ubuntu and yazrobaina I ram=n 'sudo usermod -aG squad ____' for each user individually. I ran command as superuser to add those users to the squad (-a) won't remove any existing groups.
3) Command(s) to allow squad to view the ubuntu user’s home directory contents:
- As superuser I used the code 'sudo chmod g+rx /home/ubuntu' to give the group (g) permission to read and execute (r + e).
4) Command(s) to modify share to have group ownership of squad:
- at first I ran the command 'sudo chgrp -R squad /home/ubuntu/share' which ran command as superuser, and applied (-R) command to the folder and everything inside it for the group (chgrp) and assigned squad ownership to the folder.
5) Describe your tests and commands with the user account:
- I switched user to yazrobaina to see if i could access the shared folder, and create a file inside of it. I ran 'su- yazrobaina' 'cd /home/ubuntu/share' and 'touch testmakefile.txt' which confirmed that I was able to create files inside the folder. Which /home/ubuntu gave g+rx permissions to do.
6) Describe the full set of permissions / settings that enable the user to make edits:
- sudo addgroup squad (create group)
- sudo usermod -aG squad ubuntu (add members)
- sudo usermod -aG squad yazrobaina
- squad (to check all members added)
- mkdir /home/ubuntu/share (set up folder for group)
- sudo chgrp -R squad (made squad own the folder + inside it)
- sudo chmod -R g+rwx (allowed read,edit and create files inside folder)
- cd /home/ubuntu/share (testing to see if yazrobaina can  enter in folder)
- touch testmakefile.txt (testing to see if yazrobaina can make file in folder))

## Part 5
1) Command(s) to make file using sudo:
-  'sudo touch madewithsudo.txt' commaned created a new file named madewithsudo.txt using superuser. 
2) Command(s) to make file with root:
- I ran 'sudo -i' which changes to rootshell and created file 'touch madewithroot.txt'. Then I checked to see if it worked, 'ls -1 madewithroot.txt'
3) Describe / compare ownership and permissions of files:
-  I ran to see permissions 'ls -l madewithsudo.txt madewithroot.txt' and output was '-rw-r--r-- 1 root root madewithsudo.txt'
'rw-r--r-- 1 root root madewithroot.txt'
### table of contents:
- Who can View? root,yazrobaina,ubuntu
- Who can write? root,yazrobaina,ubuntu
- Who can execute? root,yazrobaina,ubuntu
### table of madewithsudo.txt:
- Who can View? root,yazrobaina,ubuntu
- Who can Write? only root.
- Who can change permissions? only root.

4) Command(s) to modify permissions:
- I ran "sudo chown ubuntu:squad /home/ubuntu madewithsudo.txt" I used superuser to change owenership and set ubuntu as owner of squad for the madewithsudo.txt. 'sudo chmod 660 /home/ubuntu/madewithsudo.txt' I changed file permissions using numericmode making the user/owner r+w(6), making group (6) r+w and leaving others no access. (0).
5) How to give user account sudo:
- I ran command 'sudo usermod -aG sudo yazrobaina' as superuser to modify useraccount to append yazrobaina to sudo group without (-a) appending yazrobaina.
Then i switched user 'su-yazrobaina' and double checked by asking 'sudo whoami' because regular whoami didn't work. and the output was 'root'.









