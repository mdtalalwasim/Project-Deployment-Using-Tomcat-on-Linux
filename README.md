# Project-Deployment-Using-Tomcat-on-Linux
Project Deployment Using Tomcat on Linux


#### Generate War file of your Spring Boot Project: (IDE -> STS or Eclipse)
 Right Click on **project exploler** and open **terminal**
 ```bash
  mvn clean install
```
**N.B:** **war** file will generate under **target** directory inside STS or Eclipse.



#### Login to the remote server:
```bash
ssh username@hostname -p 2228

```
```bash
Example: ssh wasim@192.168.02.01 -p 2228
Example: ssh wasim@wasim.swe.net
wasim@wasim.swe.net's password: 'Input your password here'
```

Where, 
**ssh** refer to **secure shell**<br>
**username** refer to **username** like **wasim**<br>
"**-p**" refer to **port**,<br> 
**2228** refer to **port number**<br>
**ssh default port** number is **22**



for sudo privillages: 
sudo -s

Check current directory check:
```bash
pwd
/home/wasim (home directory)
```


#### 1# Copy file from your local directory into remote directory:

 	scp -P 2228 project.war wasim@wasim.swe.net:/home/wasim
  
**NB:** Just open your terminal into current directory where your project file is present & type the above command
<br>Where, **scp** refer to **Secure Copy Protocol**

  
#### 2# Remove the Old version of the project using Tomcat GUI manager app: 
First **login** to your **tomcat manager gui** with providing your **Tomcat Manager Credentials**.
Then find the project and click on **undeploy** for undeploying the old project.

#### 3# Then Move the project file to webapps Directory:
	sudo mv project.war /opt/tomcat/webapps/
Where **mv** refer to **Move**
<br>**project.war** refer to your project file

#### 4# After completing transfer the project file restart the tomcat server:
	sudo systemctl restart tomcat

# Congratulations! 
 





