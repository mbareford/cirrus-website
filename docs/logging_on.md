---
layout: section
title: New Access to Cirrus Documentation
summary: How to get logged on to Cirrus following the upgrade June 2020
---


Following the Cirrus return to service post upgrade, there have been some changes to login authentication.

Users require both a SSH key and password.  Both will have to be new before users can access the system. 

# New password

You request a new password be set using the Tier2 SAFE as follows:

Login to SAFE at [https://safe.epcc.ed.ac.uk](https://safe.epcc.ed.ac.uk). Then:

1. Go to the Menu "Login accounts" and select the Cirrus account you want a new password set.
2. On the subsequent Login account details page click the "Request Password Reset" button
3. Wait till you receive the email confirming the password reset has been completed, then
4. On the Login account details page click the "View Login Account Password" to retrieve the password set for you.

# New public key

You upload the public part of the key pair to your Cirrus machine account using the Tier2 SAFE as follows:

Login to SAFE at [https://safe.epcc.ed.ac.uk](https://safe.epcc.ed.ac.uk). Then:

1. Go to the Menu "Login accounts" and select the Cirrus account you want to add the SSH key to 
2. On the subsequent Login account details page click the "Add Credential" button 
3. Select "SSH public key" as the Credential Type and click "Next"
4. Either copy and paste the public part of your SSH key into the “SSH Public key” box or use the button to select the public key file on your computer.
5. Click "Add" to associate the public SSH key part with your account

The public SSH key part will now be added to your login account on the Cirrus system.

# Full details for logging on to Cirrus

Full details for logging on to Cirrus are included in the [documentation pages.](https://docs.cirrus.ac.uk/user-guide/connecting/)
