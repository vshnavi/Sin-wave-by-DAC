# Sin-wave-by-DAC
 Sine wave generation using DAC,using controller MSP430.

Title:	To generate sine wave using DAC module of LPC2148.	

Problem: Write a C program to create the following periodic signal using DAC module available in LPC2148 microcontroller.




Algorithm:-


a.	Start the program.
b.	Produce the sine wave using matlab.
c.	Take that array of produced sine wave and declare it globally.
d.	Insert the count in PINSEL1 and IODIR0.
e.	Using for loop take each element of array in DACR.
f.	Send that data to DAC.
g.	End.







Kits Required:	-
             
                 LPC2148  ,ARM7 Based Microcontroller Kit (ALS-SDA-ARM7-06Kit),  DSO.



Software:-  
   Keil, flash magic.
   
Solution:
1)	Given wave is the sin wave of frequency 10Hz and time period is 100msec with peak to peak 3v .We have to  generate it using DAC module in LPC2148.    
               2) LPC2148 have 10bit DAC. So, maximum count in DAC is 2^10=1024.
               3) Let’s max. voltage of sine wave=max. DAC count.
                                                 i.e. 3v=1024	
                                  so, lets  voltage=DAC count
                                         DAC count=(1024*voltage)/3
              4) So, to implement above equation we need value of voltage at each point of sine wave.
              5) For this, divide the signal in 100 parts.(Samples of sine wave should be more in order to
                   represent smooth wave)
              6) now, time between two consecutive sample is given by,
                                                  Ts=100msec/100
                                                      =1msec.
             7)  To get voltage at each sample, we have to construct a equation for sine wave.  
                  As our maximum  voltage for sin wave is 0 to 3v,so equation is,
                                           voltage(at each division)=1.5+1.5*sin(angle)
                                                       Here, total angle of sine is also divided in 100 samples.

             8)  So,angle is varied from o to 360 in 100 steps.So,we get 100 different voltage levels 
                   of sine wave  in 0 to 3volt.

             9) But we want digital count in between 0 to 1024 for DAC.So.by using equation in the 
                  Step 3 we get digital count.

           10) By performing all this math operation in Matlab code,we directly get array of all 100
                  values of corresponding 100 voltage level of sine wave.

           11) Now, if we send all this value with 1msec delay (which we counted in step 6) between 
                  them, we get our required sine waveform with 100msec period and p-p 3v. 


Matlab solution:-
clc;
i=0:360/200:360	
x=(1.5+1.5*sin(3.14/180.*i));
d=((500*x)/3);
plot(x);
figure
plot(d);



Conclusion:-
Hence we can conclude that we were successful in obtaining sine wave of required time period and voltage using DAC modul.
So,We can use DAC module as sin generator.
And as we increase the number of samples,the shape of waveform becomes smoother.   


