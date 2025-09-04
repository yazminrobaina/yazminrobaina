# Lab 02
- Name: Yazmin Robaina
- Email: robaina.3@wright.edu

//path to private key
//ssh command


## Part 2 - Bits of permissions
chmod u+r bubbles.txt
- meaning: The command "chmod u+r bubbles.txt" means to change the level  of interaction that the user has with the bubble.txt file, the u+r makes it so the user can read the file. It does not affect anyone else but that user.
- Assessment: Pretty safe command giving the user the ability to read the bubble.txt file.without the file being overly exposed. But the user might need the ability to edit it later on or what not.

chmod u=rw,g-w,o-x banana.cabana
- meaning: The command "chmod u=rw,g-w,o-x banana.cabana" gives the user of the file the permission to read and write in the file. It also removes the permission from g which is the group, the group cannot write in the banana file, they can only view it. Everyone else cannot run the file as a program.
- assessment: This is a good command that gives clear boundaries. Which makes it so the owner of the file can read + edit. While stopping others in the group from editing it giving the file good security.


