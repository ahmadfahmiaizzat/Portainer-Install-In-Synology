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

![Get started](https://github.com/user-attachments/assets/d8f3fe8f-9785-4631-ab36-1c7d02becf45)

Step 9
Click the small pencil in the Environments section on the right. 

![pencil](https://github.com/user-attachments/assets/7e11300c-449b-47de-8f46-334dc1891cd0)

Step 10
A new page will open when you click on the tiny pencil. Enter your own NAS Local IP address.In my case, 192.168.0.164 in the Public IP section and select Update environment.

![Nas ip](https://github.com/user-attachments/assets/27d8e98c-8439-488a-ac0c-069e13d0407e)

Step 11
The phrase "Environment updated" will appear in the upper right corner of your screen if everything goes according to plan.

Step 12
This is your Portainer Dashboard

![Dashboard](https://github.com/user-attachments/assets/da245314-5c95-442d-8e8c-3ddde7304141)

Step 13
Click Registries in the left Portainer sidebar, and then select + Add registry. Observe the guidelines provided in the picture below.

![Registry](https://github.com/user-attachments/assets/20ade534-fd98-49d5-99e5-f713a6eea711)

Step 14
Select "Custom registry" by clicking. Type GHCR in the Name field and ghcr.io in the Registry URL fields.
To save the configuration, select Add registry. Observe the guidelines provided in the picture below.
It should be noted that updating Docker containers via Portainer that are supplied by the ghcr.io registry requires the ghcr.io registry.

![Registry 2](https://github.com/user-attachments/assets/d2ba667b-e281-44c4-83e1-aca094b74b72)

Step 15
Repeat Step 14 , Select "Custom registry" by clicking. Enter CODEBERG in the Name box and codeberg.org in the Registry URL fields.
To save the configuration, select Add registry. Observe the guidelines provided in the picture below.
It should be noted that updating Docker containers via Portainer that are supplied by the codeberg.org registry requires the codeberg.org registry.

![Registry 2](https://github.com/user-attachments/assets/fa5fead7-6db3-41ec-b9da-5136d5b72697)

Step 16 
Repeat Step 14 , Select "Custom registry" by clicking. Type Quay.io in the Name field and Quay.io in the Registry URL fields.
To save the configuration, select Add registry. Observe the guidelines provided in the picture below.
It should be noted that updating Docker containers via Portainer that are served by the quay.io registry requires the quay.io registry.

![quay io](https://github.com/user-attachments/assets/d67b8cc2-77ac-4d35-b90b-52bcecc6c106)

Step 17
If all goes according to plan, your Registries section will resemble this:

![Registry 3](https://github.com/user-attachments/assets/9ca43b9d-5f42-445d-a7c7-954bd1de1d26)


Enjoy your Portainer!!!!!!















