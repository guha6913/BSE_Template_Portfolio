# Phone Controlled Robot Arm 
This project is basically the best combination of Software Engineering and Robotics. You get build, code, and control a robot arm and learn throughout the process. 

# About the Creator 

Hi, my name is Anusha, I go to Saratoga High School and am an incoming sophomore. I have always been interested in coding and robotics, which is why I chose this project. This project is the perfect combination of both of my interests, coding, and robotics. I was also able to use my prior experience in robotics and coding to help me throughout this project. My prior experience includes being a part of several robotics teams since 4th grade, as well as several coding classes in Python and Java. Now that I have told you about myself it is time to show you the process I went through in developing this project. 

<p align="center">
<a href="https://ibb.co/RTnrzqS"><img src="https://i.ibb.co/MkTwMmh/IMG-3164.jpg" alt="IMG-3164" border="0" height="400" width="550">
</a>  
</p>

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Anusha| Saratoga High School | Software Engineering | Incoming Sophomore  

# My Project 

This is a image of my final project. 

<a href="https://ibb.co/X3TCp56"><img src="https://i.ibb.co/tx5Jc2n/IMG-3592.jpg" alt="IMG-3592" border="0" height="400" width="600">
</a>


# My Slideshow 

<p align="center">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vS8wXpOMUI9ZGK6URx7cepFxaGjfvMK-50FsJa9imEcLtarxt_vyW_c5u4cHxphAvo3L3OUGiGmEe9h/embed?start=true&loop=true&delayms=3000" frameborder="0" width="400" height="400" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</p>

# Final Milestone
My final milestone is about my whole thinking process and journey throughout this project. In this milestone, I talk about why I picked this project, the materials I needed to build it, how my project works, challenges I faced throughout the process, and modifications I would like to do in the future. 

[![Milestone 3 ](https://res.cloudinary.com/marcomontalbano/image/upload/v1660334730/video_to_markdown/images/youtube--JB2WT9Ev7AQ-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/JB2WT9Ev7AQ "Milestone 3 ")

# Second Milestone
My second milestone is all about building and coding the actual robot arm. This requires both mechanical and software engineering. To begin with, I started assembling the base and added two types of Arduinos to the base. Then I attached a servo onto the bottom of a square plate that is held up by standoffs. Then I attached another square plate to the top of the servo which made the plate rotate. After that, I worked on the actual arm. I took another servo and attached it to another plate and attached that to the square plate that was the rotating plate. From there I continued to make the arm with many pieces like the ladder-like piece and the thing long connecting pieces. After the arm was built I started making the claw. Here I took a small rectangular plate with a rectangle and two flaps shape cut out. In this hole, I put a servo and two other pieces that would help attach the claw to the arm. Then I put another of the same plate to sandwich a part of the servo so it would stay in place. After this, I attached the two claw arms and then attached the completed claw onto the arm. Now that the actual arm is built I then made the circuit. Originally it was supposed to use the Arduinos that I had added but since that wasn't functioning properly I used a breadboard and a different Arduino. First, I attached two small yellow wires to each servos red and brown wires. I took the other end of these yellow wires and attached them to the positive and negative parts of the breadboard. Then I attached male-to-male jumper wires to the orange wire of each of the servos. These jumper wires are then attached to the Arduino. After this, I put the HC-05 Bluetooth module on the breadboard and used wires to connect it to the Arduino. This concludes the summary of Milestone 2.

[![Milestone 2](https://res.cloudinary.com/marcomontalbano/image/upload/v1660335001/video_to_markdown/images/youtube--OpxY_S4zJ_Y-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/OpxY_S4zJ_Y  "Milestone 2")

# First Milestone
My first milestone was to learn how to operate a servo motor using an app. To do this I had to use an Arduino, Bluetooth module, and jumper wires to assemble the circuit needed for the servo motor to spin. To assemble it I first connected the four pins of the Bluetooth module to the Arduino. Then I connected the servo to the Arduino.  I also had to create a Bluetooth connection code and upload it to the Arduino in order for the app to connect to the servo. To do this I first went to settings and connected the HC-05 module which cause the module to slow blink. Then I went to the app and clicked on the Bluetooth symbol and selected the device.  Once all this was done I was finally able to make the servo spin. This summarizes what I did for the First Milestone. 

[![Milestone 1](https://res.cloudinary.com/marcomontalbano/image/upload/v1659387072/video_to_markdown/images/youtube--W84QlARqhuY-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/W84QlARqhuY "Milestone 1")

# Bill of Matierials 
Down bellow if the list of matierials, where you can find them, and the cost of each indivisual item . The overall cost is about $85.83.

| Item | Qty | Price | 
| ------------- | ------------- | ------------- | 
| Arm Kit | 1  | $35.99 | 
| M3 Screw and Nut Kit | 1  | $12.69 | 
| Breadboard and wires kit | 1 | $13.99 |
| Arduino | 1 |  $23.16 |


# Schematics 
This is the wiring diagram that is needed of the servos. 
<p align="center">
<a href="https://ibb.co/TbL1mvF"><img src="https://i.ibb.co/k91JQHW/Schematics.png" alt="Schematics" border="0" height="400" width="600">
</a>
</p>

# Phone Controlled Robot Arm Code 
This is the code that i used to get the bluetooth connection and the arm moving. 

```

#include <Servo.h>
Servo myservo1;  // create servo object to control a servo
Servo myservo2;
Servo myservo3;
Servo myservo4;
int pos1=90, pos2=90, pos3=90, pos4=90;  // define the variable of 4 servo angle and assign the initial value( that is the boot posture angle value)
char val;
int incomingByte = 0;          // Received data byte
String inputString = "";         // Used to store received content
boolean newLineReceived = false; //  Previous data end flag
boolean startBit  = false;  //Acceptance Agreement Start Sign
int num_reveice=0;


void setup()
{
  myservo1.attach(3);    // set the control pin of servo 1 to 3 digital I/01
  myservo2.attach(5);    // set the control pin of servo 1 to 3 digital I/0
  myservo3.attach(6);    // set the control pin of servo 1 to 3 digital I/0
  myservo4.attach(9);    // set the control pin of servo 1 to 3 digital I/0
  
  myservo1.write(pos1);
  myservo2.write(pos2);
  myservo3.write(pos3);
  myservo4.write(pos4);
  delay(1500);
  Serial.begin(9600); //  set the baud rate to 9600
}

void loop() 
{
while (Serial.available())
  {
    incomingByte = Serial.read();              //One byte by byte, the next sentence is read into a string array to form a completed packet
    if (incomingByte == '%')
    {
      num_reveice = 0;
      startBit = true;
    }
    if (startBit == true)
    {
      num_reveice++;
      inputString += (char) incomingByte;    
    }
    if (startBit == true && incomingByte == '#')
    {
      newLineReceived = true;
      startBit = false;
    }
    
    if(num_reveice >= 20)
    {
      num_reveice = 0;
      startBit = false;
      newLineReceived = false;
      inputString = "";
    }  
  }

if(newLineReceived)
{
      Serial.println(inputString);
      if(inputString.substring(0,3)=="%4#"){
        Serial.println("Up");

         // raise the arm 
        for(pos3;pos3<100;pos3++)
        {
          myservo3.write(pos3);
          delay(5);
        }
        delay(1500);
        
      }else if(inputString.substring(0,3)=="%5#"){
         Serial.println("Close");
        // close the claw 
        for(pos4;pos4>45;pos4--)
        {
          myservo4.write(pos4);
        }
        delay(1000);
        
        
      }else if(inputString.substring(0,3)=="%7#"){

        
         Serial.println("Down");
         // Lower the arm 
         for(pos3;pos3>40;pos3--)
         {
            myservo3.write(pos3);
            delay(5);
         }
         delay(1000);

         
      }else if(inputString.substring(0,3)=="%A#"){
         Serial.println("Forward");
          //  stretch out the arm
          for(pos2;pos2<130;pos2++)
          {
            myservo2.write(pos2);
            delay(5);
          }
          delay(1000);
         
      }else if(inputString.substring(0,3)=="%B#"){
        
         Serial.println("Left");
         for(pos1;pos1<150;pos1++)
          {
            myservo1.write(pos1);
            delay(5);
          }
          delay(1000);
          
      }else if(inputString.substring(0,3)=="%C#"){
         Serial.println("Right");
         for(pos1;pos1>30;pos1--)
         {
            myservo1.write(pos1);
            delay(5);      // delay 5ms（used to adjust the servo speed）
         }
         delay(1000);
      }else if(inputString.substring(0,3)=="%D#"){
         Serial.println("Backward");
          // retracte the arm
          for(pos2;pos2>80;pos2--)
          {
            myservo2.write(pos2);
            delay(5);
          }
          delay(1000);

      }else{
        Serial.println("Default");
         // open the claw
       for(pos4;pos4<120;pos4++)
       {
         myservo4.write(pos4);
       }
        delay(1000);
      }
      inputString = "";   // clear the string
      newLineReceived = false;
}   
   
}

```
