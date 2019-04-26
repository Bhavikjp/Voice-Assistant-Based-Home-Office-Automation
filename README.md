# Voice-Assistant-Based-Home-Office-Automation
You might have used google assistants app to play music, to get some information and for other stuff. But your google assistant can do more, than these. Now you can use your google assistant to control your home appliances (here we have LED in place of home appliance) by just saying: "OK Google, Lights ON" That's it.

You might have used google assistants app to play music, to get some information and for other stuff. But your google assistant can do more, than these. Now you can use your google assistant to control your home appliances (here we have LED in place of home appliance) by just saying: "OK Google, Lights ON" That's it.

REQUIREMENT :

HARDWARE: Bread Board Wemos D1 Mini Board, Led, Resistors, Relay Module (Need to Buy If We Are Connecting Home Appliance), USB Cable

SOFTWARE: Arduino Ide, Google Assistant and IFTTT App in Your Smart Phone, an Active Account on Adafruit.io Mqtt Broker LIBRARY:ADAFRUITIO_MQTT_LIBRARY YOU CAN DOWNLOAD IT FROM HERE :https://github.com/adafruit/Adafruit_MQTT_Library

Control your home appliances from anywhere with your Google asssistant!!!https://github.com/Bhavikjp/Voice-Assistant-Based-Home-Office-Automation/blob/master/images/wemos%20d1%20mini.jpg

Let's start your journey with our OPENCORNER’s hardware kit!! Open that Kit box. What do you have?? As you can see in that box there is one blue colour Board along with 2 LEDs, few resistors and jumper wires as shown below: 

Introduction:

You might have used google assistants app to play music, to get some information and for other stuff. But your google assistant can do more, than these. Now you can use your google assistant to control your home appliances (here we have LED in place of home appliance) by just saying:

"OK Google, Lights ON"

That's it.

Let’s see how to make this possible,

REQUIREMENT:

HARDWARE: Bread Board Wemos D1 Mini Board, Led, Resistors, Relay Module (Need to Buy If We Are Connecting Home Appliance), USB Cable

SOFTWARE: Arduino Ide, Google Assistant and IFTTT App in Your Smart Phone, an Active Account on Adafruit.io Mqtt Broker PROCESS: Hardware Connection Getting Arduino IDE ready for programming Configuring Adafruit.io Coding IFTTT (connecting google assistant with Adafruit.io MQTT broker)

Hardware Connection:

•	As you can see on the board there is lots of pin available (i.e. analog pins, digital pins, TX, RX, 5V, 3.3 and ground pins)

•	Here we are going to use digital pins D1 and D2.

•	Let’s connect components as shown in below figure:

4 in hardware connection 1

5 in hardware connection 2

If you have relay module than make connection as shown in figure with your home appliance. (here we are using bulb)

WEMOS D1 mini                  Relay Board


   5V                 -----       VCC
   
   
  GND                 -----       GND
  
  
 IN (signal pin)    -----    D1 or *any digital pin
(Note: If you are using any other pin you have to change that pin configuration in given code.)

Getting Arduino IDE ready for programming:

6 getting arduino ide ready for programmuing

Download ARDUINO IDE from here (according to your system) if you have windows system then just click here Install ARDUINO IDE to your system.

Once setup is done we need to configure ESP8266 to use it with Arduino IDE

Now Open ARDUINO IDE.

Step 1: Copy this link http://arduino.esp8266.com/stable/package_esp8266com_index.json Now go to file->preferences->Additional Boards Manager URLs 7 preferences and additional board manager

  Step 2: Go to Tools->boards->boards manager, search ESP8266 and install esp8266 board.

8 installing esp8266 in board manager

Once installation is done you should be able to see ESP8266 Modules in Toolsboards. If "Yes" then Congratulations, you are ready to code!!

Let’s Start Coding......

Step 3: Connect Wemos D1 mini to your computer via USB cable

Step 4: Download this code and open with Arduino IDE

Step 5: Go to Tools->boards->ESP8266 and Select Wemos D1 mini

Step 6: Select port COMX of your board To check Port Go to device manager, you should be able to see your device under ports along with port number

9 device manager port

Here wemos d1 mini is connected on COM6  Now select COM port on Arduino ide like this:

10 port selecting in arduino
 

Configure Adafruit.io

Step 8: Now we need a MQTT broker. There are many broker for MQTT but we have used Adafruit MQTT broker. It’s quite simple and its UI is also great. To use Adafruit MQTT broker, first of all you need to make an account on Adafruit.io.

First sign up for ACCOUNT 11 configuring adafruit io 1

Then LOGIN on Adafruit.io. You can see something like this after login.

12 configuring adafruit io 2   3. Click on Action and Create new Dashboard as shown here 13 configuring adafruit io 3

Here we are creating dashboard name testing.

14 configuring adafruit io 4   4. Now you can see "testing “dashboard that we have created:

15 configuring adafruit io 5

As you can see there are many options available on the right corner of the page to edit the blocks, add new blocks, get the key, etc.

Now we will start with making a new button on the dashboard. For that click on the second button i.e. create a new block. It will show this window. There are number of blocks to be added in this window like toggle button, push button, slider etc. In our project we will be using the first block i.e. toggle button. Click on create button and you will get following options.
16 configuring adafruit io 6

  6. Than you have to provide feed name which should be unique because this feed name is nothing but the topic which clients will be subscribing. 17 configuring adafruit io 7

I have given name of the feed as light. Then click the create button. Created feed name will be added, then select that feed name. Then click on next step. You will see something like this.

Fill the details as given in following image
18 configuring adafruit io 8

  8. You can see toggle button with "LIGHT" as a topic and "1" and "0" as the values. 19 configuring adafruit io 9

9.Follow this same procedure to create topic "light1" then you will see two toggle buttons on dashboard as follow. 20 configuring adafruit io 10  

Now click on KEY icon on right corner of the dashboard. You will see prompted window showing USERNSME and KEY. Note: Copy and paste these details somewhere because we are going to use these detail in code for connection purpose. 21 configuring adafruit io 11
That’s it. You are done with the broker side. No complexity, nothing. Only simple and great UI and that’s why we like adafruit broker. You can even drag and resize the block according to your need.   Coming back to Arduino Step9: Download “GoogleAssistance_demo” code from here by clicking on “Clone or download” (download zip). Unzip this folder and open that code in Arduino IDE. Now download “Adafruit_MQTT_Library” from here. Click on “Clone or download.”

22 coming back to arduino downloading adafruit library 12

Now follow this step to add this library into our ARDUINO IDE. Go to Sketchinclude libraryadd zip library than navigate to that library then open. You get message if library is successfully added to Arduino.

Now, Make following changes, write down you router SSID AND PASSWORD at

#define WLAN_SSID “YOUR ROUTER SSID" #define WLAN_PASS "YOUR ROUTER PASSWORD" 23 changes in arduino code 13

Copy and place your adafruit’s USERNAME and KEY at this location in code.

#define AIO_USERNAME "YOUR USERNAME" // WRITE YOUR ACCOUNT USERNAME HERE #define AIO_KEY "YOUR PASSWORD" // WRITE AUTOGENERATED KEY HERE

Step10: Click COMPILE button If you don’t get any error code can now be uploaded

Step11: Click UPLOAD button Step12: Open Serial Monitor by clicking on search type icon as you can see in right corner. A small window is prompted as shown below. Make configuration as highlighted in figure. As you can see wifi and mqtt both are connected.

24 serial monitor 14

IFTTT APP

Now install IFTTT app in your smart phone. Make an account on IFTTT applet service.

IFTTT stands for “IF THIS THAN THAT” If we relate this to our example if this thing is happening than do this thing. In this process we going to merge our “google assistant” to our “Adafruit mqtt broker” Using IFTTT applet service. So when we say “ok google lights on” this phrase send (publish) data to mqtt broker feed And our device which is already subscribed to this feed or topic will receive this data and lights becomes OFF.

Let’s see how to merge both this services.

Step 1: First open IFTTT application that you have already installed. Step 2: Now Go to “My Applets”. Step 3: On “My Applets”, in the right corner there is a “+” sign, click on that to create your own Applet.

25 iftt myapplet 1

Step 4: Now click on +this and search for GOOGLE assistant service and click on google assistant service to add as our input.Now click on say a simple phrase.   26 iftt myapplet2 27 iftt myapplet 3
28 iftt myapplet 4 29 ifttt myapplet5

Now you have got one screen with some question. 1st Question: What do you want to say? Just write which command you want to give to turn ON the light. Write “lights ON” or”turn on the light google” 2nd Question: What do you want the assistant to say in response? You can write any phrase here like “Ok done lights are on” or “JO HUKUM
MERE AAKA” Then click on create trigger. Now you can see google assistant is added in place of +this. 30 ifttt myapplet6

31 ifttt myapplet 7
Step 5: Now click on +that and search for adafruit and click on ADAFRUIT service. Then click on send data to adafruit IO button Now you will see something like this: Here, we have to provide feed name that we have already created on ADAFRUIT. Just click on below feed name you will see light and light1 feed that we have created Select light feed. Now type “1” in data to save field to turn on the light. (If you remember we have given 1 at button on text at toggle button configuration on adafruit.io) Now click on create action. Now click on finish. 32 iftt myapplet 8 33 ifttt myapplet 9

Step 6: After that you will be prompted to adafruit site now click on authorize to give access.

34 ifttt myapplet 10

Now go to the dashboard and click on “services”. 35 ifttt myapplet 11

You will see lots of services, now click on get started button given below IFTTT service.

36 ifttt myapplet 12

You can see IFTTT is connected with your adafruit account. 37 ifttt myapplet 13

Follow this whole procedure again from Step2 to Step5 to create another applet for turning off the light. You just have to change 2-3 things. Give input command “lights off” at google assistant setting as discussed above for “lights on” and write “0” at data to save field this time at send data to adafruit page in IFTTT app   Everything is done.now, just say “ok google” then you will see something as shown below on your mobile screen

38 google assistant last image

Now just say “lights on” (say whatever you write at the time of configuration). If you have any doubt any query please feel free to ask about this task or about anything related to IoT. Just give us a chance to open door of internet of things technology for your smart future.
