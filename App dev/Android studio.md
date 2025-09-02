- name the project
- also the package name(check it on playstore so that no other app has the same package name  ex: com.calculator)
- round icon if the person has a launcher which rounds the icons(looks shit so provide our own round icon)
- ## Intro to Android (skip)
- Android- open source, linux based , operating system
- OS- software program that enables hardware to communicate with software
	- interface between user and hardware
- User > Apps > OS > Hardware
- Linux- family of open source software operating systems built on linux kernal
- open source- license free, open for all, reusable and changable (available free of charge)
## Android versions
- to resolve issues in previous versions, we bring new versions
- in the beginning names used to be based on sweet names in alphabetical order , like cupcake, donut, eclair , etc
- now it's just boring Android 10, Android 11 etc
## Front and Backend
- Front End (also c/a ui)
	- XML and Android programming(Java/Kotlin)
	- brings data/req from server
- Back End
	- database and code
	- SQLite for android
## Static and Dynamic apps
- Static
	- not reliant on internet connection
	- apps, downloaded once, updated periodically
	- calculator
- Dynamic
	- depends on internet, online server or database
	- if there's no internet , it shows last loaded session(static)
	- retrieve data updates from main server
	- currency converter, news etc
## Run time and Compiler time erorrs
- debugging
## Apk file
- Android Application package
- executable file for android operating sytems, like .exe file in windows operating sytems
- consists of
	- Application code(.dex file)
	- manifest file
	- assets
	- resource files
- the files
	- manifests
	- java+kotlin- contain the main file
	- res- UI file
- if your gonna create a folder in res , make sure the name don't start with number/ special characters, has spaces and NO CAPITAL LETTERS TOO
- ![[Pasted image 20241001131404.png]]
	-  drawable- put all images in this (.jpeg, .png, .svg) 
		- import the pic by  new > vector assets
	- layout- has main xml file
	- mipmap- got icons
	- values- got colors and strings xml files
- for icons we use .svg (they're like vectors ig?) and for images we ue .png or .jpeg
## Android virtual devices (emulator)
- for virtual android environment
- ADK manager/ Device manager

> [!NOTE]
> - ==xmlns:tools="http://schemas.android.com/tools"> this is there in my code but in the tut it's showing package ="com.developer.myfirstapp" ???==

- testing: 
	- test - memory and how else to more optimize it
	- android test - run time test
- ![[Pasted image 20241023222756.png]]
- sdk manager in settings
	- ![[Pasted image 20241103215611.png]]
> [!NOTE]
> - Oracle jdk need license and makes you pay when you need to commerically make a app, so use openJDks for it
- heirarchy 
	- ![[Pasted image 20241103220908.png]]
## AndroidManifest
- All component app uses
- app needs permission from users? put them here
## Kotlin + Java
- only first one is imp
- ![[Pasted image 20241103221227.png]]
- All source code in MainActivity.kt
- res(generated) - ignore those generated folders, cannot even open it
- to create layout file
	- ![[Pasted image 20241103222135.png]]
	- choose resource file
	- for activity xml
	- ![[Pasted image 20241103222209.png]]
	- and choose constraintLayout
- res- short for resources
	- drawable- contain all images, icons, graphical configuration files
	- layout (not present now)- has activity_main.xml (you can create it yourself)
	- mipmap- icons when you want to publish your app (app launcher icons)
	- values 
		- colors.xml- to create color palette for our app
		- strings.xml- global strings for our app
		- theme.xml - themes
- gradle - build system for android (takes all components and put them into executable app)
	- only first two are important
	- ![[Pasted image 20241103222339.png]]
	- in the second one dependencies exist and directly affect the build quality of app
	- dependencies is imp when your using third party libraries
## Activity
- Activity- single screen on device (kotlin class)
- inherits from ComponentActivity() 
- onCreate() fxn is from ComponentActivity() 
- onCreate() fxn- main fxn of android (like fun main())
- Activity Stack - first-> second> third  - this is how android remembers
### Activity Life Cycle
 - ![[Pasted image 20241103225226.png]]
	 - onCreate( )- main fxn - fxn where u instantiate obj and initialize the variables
	 - onStart() - when the variables become visible
	 - onResume() - Activity start interaction with user , activity on top of activity stack 
	 - onPause( )- when activity looses foreground state( still running in bg)
	 - onStop()- when the activity is killed (like when app crashes, or system kills it when higher priority app need resources/ memory)
	 - onRestart() 
	 - onDestroyed()- when app shuts down
- Always save your data on onPause() (cuz onStop is not gaurenteed to be called, onPause() is )

> [!NOTE] Title
> CTRL + O to get override fxns
- to override a certain activity you just write it
	- ![[Pasted image 20241103225346.png]]
	- ![[Pasted image 20241103225502.png]]
