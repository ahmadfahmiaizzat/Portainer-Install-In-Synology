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

1. General Tab : Enter "Install Portainer" in the Task field. Take out the "Enabled" check box. Choose the root user.
2. Schedule Tab: After choosing "Run on the next date," choose "Do not repeat."
3. Task Setting Tab : After selecting "Send run details by email" and entering your email, copy and paste the following code (Task Field) into the Run command field. Click OK after that.

docker run -d --name=portainer \
-p 8000:8000 \
-p 9000:9000 \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /volume1/docker/portainer:/data \
--restart=always \
portainer/portainer-ce   

![task field](https://github.com/user-attachments/assets/3a903d73-06d8-4f4d-97af-95e3fd8b5d78)

Step 5
On Step 4, a new warning pop-up window will appear after you click OK. Press OK.
Enter your DSM Password after clicking OK, then click Submit.

Step 6
In STEP 5, after clicking Submit, choose your "Install Portainer" Task and click the "Run" button. Click OK when prompted to launch Install Portainer.

Step 7
Navigate to http://Synology-ip-address:9000 in your browser. Select a robust password and username, double-check the password, then click "Create user."

Step 8
To begin using the local environment in which Portainer is running, click Get Started. 

