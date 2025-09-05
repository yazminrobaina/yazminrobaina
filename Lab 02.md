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





