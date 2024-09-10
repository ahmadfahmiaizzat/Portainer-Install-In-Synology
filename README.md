# Portainer-Install-In-Synology
Portainer Install Using Task Scheduler &amp; Docker

Step 1
Install Container Manager via the "Package Center" on Synology. If your DSM version is less than 7.2, look for Docker rather than Container Manager.

Step 2
Locate and open the docker folder in File Station. Make a new folder called portainer inside the docker folder. Observe the guidelines provided in the picture below.
Remember to only use lowercase letters—never uppercase.

![image](https://github.com/user-attachments/assets/2052ab1e-2985-4a1a-88d0-72bdeaf2aa59)

Step 3
Navigate to Task Scheduler / Create / Scheduled Task / User-defined script in the Control Panel. Observe the guidelines in the image below.

![image](https://github.com/user-attachments/assets/aedde344-3efe-4668-b2c3-88e18862c6ff)

Step 4
Clicking User-defined script will launch a new window. Observe the guidelines listed below:

General: Enter "Install Portainer" in the Task field. Take out the "Enabled" check box. Choose the root user.
Timetable: After choosing "Run on the next date," choose "Do not repeat."
Configuring the Task: After selecting "Send run details by email" and entering your email, copy and paste the following code into the Run command field. Click OK after that.
