Under Search for services, type in and then click EC2.
In the left-hand EC2 Dashboard navigation menu, click Instances.
Click on the Launch Instances button.
Under Step 1, click Select against Amazon Linux 2 AMI (HVM).
Under Step 2, select t2.micro and click on the Next button at the bottom.
Under Step 3, select Default for Network.
Select any Subnet in the Subnet dropdown. 
For Auto-assign Public IP, select Enable.
Click on the Next button at the bottom.
Under Step 4, click on the Next button at the bottom.
Under Step 5, add a tag with key = Name & value = Test Instance. Click on the Next button at the bottom.
Under Step 6, Create a new Security Group and it should have rules for port 22 & 80 incoming from anywhere (0.0.0.0/0). Click on the Review & Launch button at the bottom.
Under Step 7, Click on Launch button. 
Create a new key pair, give it a name and download it. After that click on the Launch Instances button. 
Select the launched instance and press on the Connect button. Execute the following command after you have SSHed into the instance (to install the web server and then start the service). 
sudo yum install -y httpd
sudo systemctl enable httpd
sudo service httpd start
In a browser window, try to access the website using the EC2’s Public IP or Public Hostname (on port 80). Ensure that you use the HTTP url.  
Stop this instance and then create an AMI of it. Select the instance and explore the Actions > Image & Templates > Create Image button at the top. 
Navigate to AMIs from the left hand menu. 
Once the AMI is Available, select it and launch another instance from the AMI using the button given above (after this, follow the above steps 5 to 11). 
Check if all your changes persist in the new EC2 instance? (i.e. Webserver installation). You can check this by opening the new instance’s Public IP/hostname from a browser. 
After completing the above steps, terminate all the EC2 instances. It will disappear from the console after an hour.
Look at the menu items on the left side for AMI, Volumes & Snapshots. 
Deregister all the AMIs.
Delete all the snapshots from your account.
Delete all the volumes from your account. 
