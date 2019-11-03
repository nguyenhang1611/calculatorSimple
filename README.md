# calculatorSimple: how to run on local machine (MAC os)
1. Install Java 11
2. Install ANDROID SDK (Studio)
3. Install Appium Desktop
4. Clone code to local machine and run

```
1. Install JAVA JDK:
	- Download Java 11.
	- Setup Java 11 and Environment Variable. 
	- Open terminal and check Java JDK version by command: java –version
```
```
2. Install ANDROID SDK (Studio)
	- Download ANDROID SDK
	- Setup Environment Variable. 
```
 
```
4. Clone code to local machine and run:
	(1) Clone code from Github. Link: https://github.com/nguyenhang1611/calculatorSimple.git
	(2) Start Appium Server
	(3) Run "calculator/src/test/resources/mobile-debug.apk" in Android Studio with device "Galavy Nexus API 29 (Android 10, API 29)" 
	(4) Open terminal => Check device name on local machine: adb devices
	 Ensure that value of "deviceName" parameter in testng.xml file is same as device name above
	(5) Open terminal and cd to folder contain pom.xml file
	(6) Run command: mvn clean install

```

# calculatorSimple: how to run on Jenkins
1. Install Jenkins
2. Install Plugin, Config Global Tools
3. Create and Config Jenkins Job
4. Run Jenkins Job and check result

```
1. Install Jenkins
     - Download Jenkins and Setup. Link: https://jenkins.io/download/	      
```
```
2.  Install Plugin, Config Global Tools:
     - Install Maven Integration Plugin: "Manage Jenkins" => "Manage Plugins" => "Available" => Install "Maven Integration" and Restart Jenkins
     - Config JDK, GIT, Maven: "Manage Jenkins" => "Global Tool Configuration"
       (1) JDK: Config "JAVA_HOME" (is $JAVA_HOME of local machine)
       (2) Git: Config "Path to Git executable" is 
       (3) Maven: TICK "Install automatically" => Select "Version 3.5.4"
```
 
```
3. Create and Config Jenkins Job:
	- Create Job: "New Item" => Input project name is "Maven Project" => Select "Maven Project" => OK
	- Config Job: Click menu icon at the right side of "Maven Project" => Select "Configure":
	  (1) Click "Source Code Management" Tab => Select "Git" => Setting:
	  Repository URL: hhttps://github.com/nguyenhang1611/calculatorSimple.git
	  Branch Specifier (blank for 'any'): */master
	  (2) Click "Build" Tab => Setting:
	  Root POM: pom.xml
	  Goals and options: test
	  (3) Click "Apply" => Click "Save"
```

```
4. Run Jenkins Job and check result:
	- In Jenkins server machine:
	  (1) Start Appium Server
	  (2) Run "calculator/src/test/resources/mobile-debug.apk" in Android Studio with device "Galavy Nexus API 29 (Android 10, API 29)" 
	  (3) Open terminal => Check device name on local machine: adb devices
	   Ensure that value of "deviceName" parameter in testng.xml file is same as device name above
	- On Jenkins homepage:
	  (1) Run Job: At the homepage, Click "Maven Project" => Click "Build Now"
	  (2) Check Result: At "Build History" item => Click the build item(ex: #1) => Click "Console Output"
```
