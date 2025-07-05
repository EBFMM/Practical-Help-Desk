# Practical Help Desk
> **Ticket #4561932:** Computer won't power on
> <br><br>**Assigned:** Admin&nbsp; **Created:** 02/15/2025&nbsp; **Status:** Open
> <br><br> **Comment:** Hello, after returning from the weekend my computer won't power on. When I press the power button it doesn't do anything, it doesn't make any sounds and there is nothing displayed on the screen. I can't even try turning it on and off again, so I don't know what to do, please help. 

Solution Methodology:
1. Check power cable is correctly plugged in, if plugged into an extension (power bar) check that it hasn't been powered off and check PSU power switch is in ON position.
2. Verify both outlet and power bar are functioning properly, could plug in a known working device to test.
3. Open computer case, check for any damage to power button and verify the connections from the physical power button to MOBO are connected, try unplugging nd re-plugging them. If that doesn't work consult manual to verify the power ON pins and try to manually jumper them.
4. Check CMOS battery and reset CMOS either by unplugging battery or using the jumpers.
5. Check PSU connections to MOBO are okay, visually inspect PSU for any visible signs of damage.
6. Test PSU or if that is out of scope of duties replace with known functioning PSU.
7. Test MOBO or if that is out of scope of duties replace with known good MOBO.
<br>

> **Ticket #4561933:** Add User to Windows Computer
> <br><br>**Assigned:** Admin&nbsp; **Created:** 02/15/2025&nbsp; **Status:** Open
> <br><br> **Comment:** Hello admin, could you please add a local user "Richard" to the Windows computer. Create the account so that the user will have to change their password the first time they login. In addition, please make the user a local administrator.

Solution Methodology:
1. The local users and groups manager service (lusrmgr) allows us to perform administrative tasks on a Windows computer as a local administrator user. Open the Run dialog --> search 'lsrmgr.msc'.
2. In 'Users' Folder right click to create a new user named 'Richard', set a password and make sure the option 'User must change password at next logon' is checked.
3. In 'Groups' Folder select the 'Administrators' group and add Richard to the group. Ensure to select 'apply' to these changes.
4. Restart the computer. Once logged into new user, verify the user's adminstrative privileges by opening the command line as an administrator (right click) and accepting UAC prompt.
<br>

> **Ticket #4561934:** Add Users to Linux Host
> <br><br>**Assigned:** Admin&nbsp; **Created:** 05/15/2025&nbsp; **Status:** Open
> <br><br> **Comment:** Hello admin, please add two users to the Ubuntu Linux Host, Bertram and Erlich (leave all additional details such as last name, room number and phone numbers blank). Please create a password for each of them and expire their password so they need to create one on their first login. Also please create a new folder in the root directory called "Confidential". Make root the owner of the folder with full permissions, however, allow Bertram and Erlich full permissions to the folder. Ensure that everyone else on the computer has no permissions so they can't access the folder. Thanks!

Solution Methodology:
1. Add users Bertram and Erlich using the command 'sudo adduser bertram' and set an initial password. Then 'sudo adduser erlich' and set an intial password.
2. Expire passwords using 'sudo passwd --expire bertram' and 'sudo passwd --expire erlich' so that a new password must be created upon first login. 
3. The command 'cd /' will take you to root directory, from here 'sudo mkdir Confidential' will create a new directory 'Confidential' in the root directory.
4. Create a group for the created users using the command 'sudo addgroup confidential', add bertram and erlich to this group using 'sudo usermod -aG confidential bertram' and 'sudo usermod -aG confidential erlich'.
5. Owner is already set as root, give Bertram and Erlich full permissions by changing the directory group using 'sudo chgrp confidential Confidential' Owner (root) will have full permissions read(4)+write(2)+execute(1)=7, the group will have same permissions. Everyone else is given no permissions refelcted by value of 0 using the command 'sudo chmod 770 Confidential' to set these permissions.
<br>
