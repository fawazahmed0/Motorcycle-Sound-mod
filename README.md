# Motorcycle-Sound-Mod-Using-Arduino

I always wanted to create a prototype using arduino, which can be attached to any motorcycle and it will produce harley like sound using speakers when raising accelerator

You can see how it works from the link below:
 
 [![Youtube Video Link](https://img.youtube.com/vi/q3Sr57Ecp1U/0.jpg)](https://www.youtube.com/watch?v=q3Sr57Ecp1U)
 

I am using TMRpcm sound library to achieve this.

Refer:

 https://github.com/TMRh20/TMRpcm
 https://github.com/TMRh20/TMRpcm/wiki

you have to do some modifications in this library,these are the things you have to modify to allow frequency change:


Edits to be done in library files

Open pcmConfig.h in TMRpcm library



put

     unsigned int resolution; 
under public variables:

put 

    timerSt();
    
under public functions:

add

    unsigned int orgsamplerate;
    
under public variables


Open TMRpcm.cpp

comment the following lines

    //SAMPLE_RATE = sFile.read();
 
    //SAMPLE_RATE = sFile.read() << 8 | SAMPLE_RATE;
and add the following

    orgsamplerate = sFile.read();
  
    orgsamplerate = sFile.read() << 8 | orgsamplerate;

I have uploaded the modified files also.



My Arduino Program is increasing the pitch and at the same time volume of bike sound file. This gives us the effect of a motorcycle. Use the program in Arduino IDE

Program is based on Arduino Mega, you can also use this program in other boards ,by doing some modifications.

Here is the link for Motorcycle Audio Files:

Modified Sounds:

https://drive.google.com/drive/folders/0ByhLwJ0psErqcmpsWE9PWmxXOUU?usp=sharing

Original Sounds:

https://drive.google.com/drive/folders/0ByhLwJ0psErqX1dJR250S3lDWDQ?usp=sharing

