# Phone Controlled Robot Arm 
This project is basically the best combination of Software Engineering and Robotics. You get build, code, and control a robot arm and learn throughout the process. 

# About the Creator 
Hi my name is Anusha, i go to Saratoga High School and i am a incoming sophomore. I have always been interested in coding and robotics, which is why i chose this project. This project is perfect combination of both of my interests, it helps me learn new things as well as use my prior expieeriance. When i say prior expieriance i mean being a part of robotics teams since i was in 4th Grade. I also have taken several coding class in Python and Java. So that is a little about me and now i will show you my project and the process i went through to make it. 

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
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vS8wXpOMUI9ZGK6URx7cepFxaGjfvMK-50FsJa9imEcLtarxt_vyW_c5u4cHxphAvo3L3OUGiGmEe9h/embed?start=true&loop=true&delayms=3000" frameborder="0" width="600" height="400" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</p>

# Final Milestone
My final milestone is about my whole thinking process and journey throughout this project. In this milestone i talk about why i picked this project, the matierials i needed to build it, how my project works, challenges i faced throught the process and modifications i would like to do in the future. 

[![Milestone 3 ](https://res.cloudinary.com/marcomontalbano/image/upload/v1660334730/video_to_markdown/images/youtube--JB2WT9Ev7AQ-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/JB2WT9Ev7AQ "Milestone 3 ")

# Second Milestone
My second milestone is all about building and coding the actual robot arm. This requires both mechanical and softeare engineering. To begin with i started assembling the base and added two types of arduino's onto the base. Then i attached a servo onto the bottom of a square plate that is held up by standoffs. Then i attached another square plate to the top of the servo which made the plate rotate. After that i worked on the actual arm. I took another servo and attached it to another plate and attached that to the square plate that was the rotating plate. From there i continued to make the arm with many pieces like the ladder like piece and the thing long connecting pieces. After the arm was built i started making the claw. Here i took a small rectangular plate with a rectangle and two flaps shape cut out. In this hole i put a servo and two other pieces that would help attach the claw to the arm. Then i put another of the same plate two sandwhich a part of the servo so it would stay in place. After this i attached the two claw arms and then attached the completed claw onto the arm. Now that the actual arm is built i then made the circit. Originally it was supposed to use the arduinos that i had added but since that wasn't functioning properly i used a breadboard and a different arduino. First i attached two small yellow wires to each servos red and brown wires. I took the other end of these yellow wires and attached it to the positive and negative parts of the breadboard. Then i attached mate to male jumper wires to the orange wire of each of the servos. These jumper wires then attached to the arduino. After this i put the HC-05 Bluetook module to the bread board and used wires to connect it to the arduino. This concludes the summary of Milestone 2.

[![Milestone 2](https://res.cloudinary.com/marcomontalbano/image/upload/v1660335001/video_to_markdown/images/youtube--OpxY_S4zJ_Y-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/OpxY_S4zJ_Y  "Milestone 2")

# First Milestone
My first milestone was to learn how to opperate a servo motor using a app. To do this i had to use a arduino, bluetooth module, and jumper wires to assemble the circut needed for the servo motor to spin. To assemble it i first connected the four pins of the bluetooth module to the arduino. Then i connected the servo to the arduino.  I also had to create a blutooth connection code and upload it to the arduino in order for the app to connect to the servo. To do this i first went to settigs and connected the HC-05 module which cause the the module to slow blink. Then i went to the app and clicked on the bluetooth symbol and selected the device.  Once all this was done i was finally able to make the servo spin. This summerizes what i did for the First Milestone. 

[![Milestone 1](https://res.cloudinary.com/marcomontalbano/image/upload/v1659387072/video_to_markdown/images/youtube--W84QlARqhuY-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/W84QlARqhuY "Milestone 1")

# Bill of Matierials 
Down bellow if the list of matierials, where you can find them, and the cost of each indivisual item . The overall cost is about $85.83.
<p align="center">
 | Item | Qty | Price | 
| ------------- | ------------- | ------------- | 
| Arm Kit | 1  |  $35.99| 
| M3 Screw and Nut Kit| 1  |$12.69 | 
| Breadboard and wires kit| 1 | $13.99 |
|Arduino| 1 |  $23.16 |
</p>

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
