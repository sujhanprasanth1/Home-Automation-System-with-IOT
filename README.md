# Home-Automation-System-with-IOT

# AIM: 
  To make a Lamp at home (230 V AC) On / Off using Arduino UNO R4 WiFi board, IFTT Google Assistance and Blynk IoT mobile application.          
           
# COMPONENTS REQUIRED:
PC/Laptop with Internet connection
Arduino UNO R4 WiFi board
USB cable compatible with Arduino UNO R4 WiFi
Wi-Fi connection (mobile hotspot or Wi-Fi router)
Mobile phone with Blynk IoT app installed
Arduino IDE
Blynk account
Built-in LED of Arduino UNO R4 WiFi

## Theory: 
Blynk is an IoT platform that allows microcontroller boards to be controlled and monitored through a mobile application over the Internet. It provides a graphical interface using widgets such as buttons, switches, displays, and gauges.

In this experiment, the Arduino UNO R4 WiFi is connected to a Wi-Fi network and linked to the Blynk IoT platform. A button widget in the Blynk mobile application is used to control the built-in LED of the Arduino UNO R4 WiFi remotely.

When the button in the Blynk application is switched ON, a command is sent through the Internet to the Arduino UNO R4 WiFi, causing its built-in LED to turn ON. When the button is switched OFF, the command is sent to the board and the LED turns OFF.

The Arduino UNO R4 WiFi has built-in Wi-Fi connectivity, so no external Wi-Fi module such as ESP8266 is required. Since the experiment uses the built-in LED, no external relay or AC bulb is required.
# PROCEDURE:

Connect the Arduino UNO R4 WiFi to the PC/laptop using a suitable USB cable.
Install and open Arduino IDE on the computer.
Install/select the Arduino UNO R4 WiFi board from the Arduino board package.
Install the Blynk library in Arduino IDE.
Download and install the Blynk IoT application on the mobile phone and create/login to a Blynk account.
Create a new Blynk template/device and add a Button widget.
Configure the button as a switch and assign a virtual datastream, such as V0.
Configure the Wi-Fi SSID and password in the Arduino program along with the required Blynk authentication details.
In the Arduino program, configure the built-in LED as the output and associate the Blynk button with the LED control.
Select Arduino UNO R4 WiFi as the board and select the appropriate COM port.
Compile and upload the program to the Arduino UNO R4 WiFi.
Connect the Arduino UNO R4 WiFi to the Internet through a Wi-Fi network or mobile hotspot.
Open the Blynk application on the mobile phone.
Press the ON button in the Blynk application. The command is sent through the Internet to the Arduino UNO R4 WiFi, and the built-in LED turns ON.
Press the OFF button. The Arduino receives the command and the built-in LED turns OFF.
Thus, the built-in LED of the Arduino UNO R4 WiFi is successfully controlled remotely using the Blynk IoT application.

# CIRCUIT DIAGRAM:

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/707cbbff-a867-45bf-92d3-786a3244d2ab" />


 
# PROGRAM:
```
#define BLYNK_TEMPLATE_ID "TMPL3FC5OeIaF"
#define BLYNK_TEMPLATE_NAME "LED Control"
#define BLYNK_AUTH_TOKEN "YOUR_NEW_AUTH_TOKEN"

#define BLYNK_PRINT Serial

#include <WiFiS3.h>
#include <BlynkSimpleWifi.h>

char ssid[] = "YOUR_WIFI_NAME";
char pass[] = "YOUR_WIFI_PASSWORD";

BLYNK_WRITE(V0)
{
  int value = param.asInt();
  digitalWrite(LED_BUILTIN, value);
}

void setup()
{
  Serial.begin(115200);

  pinMode(LED_BUILTIN, OUTPUT);
  digitalWrite(LED_BUILTIN, LOW);

  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);
}

void loop()
{
  Blynk.run();
}
 ```
# Output:

<img width="1280" height="960" alt="WhatsApp Image 2026-08-20 at 10 34 43 AM" src="https://github.com/user-attachments/assets/ce863ea4-81a7-42bd-9fca-b6898f65a17c" />

https://github.com/user-attachments/assets/3767ff62-93f4-467e-82c5-7a1dc9634ca3

## Result:
The Arduino UNO R4 WiFi built-in LED was successfully controlled remotely using the Blynk IoT application. When the Blynk button was switched ON, the built-in LED turned ON, and when switched OFF, the LED turned OFF successfully.




