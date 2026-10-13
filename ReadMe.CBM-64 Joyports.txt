 There are two addresses to read joystick values, one for each control port. Joystick 1 is read at address 56321, and joystick 2 with 56320.

Due to the way port 1 conflicts with keyboard input on the CIA chip, most programmers have traditionally prefer port 2.	

=================================================================================================================================


1  Up
2	Down
3	Left / Paddle Fire
4	Right / Paddle Fire
5	Paddle Y / Potentiometer
6	Fire / Light Pen
7	5v
8	Ground
9	Paddle X / Potentiometer

=================================================================================================================================

Reading Both Joysticks Program: 

10 j1=not(peek(56321)):j2=not(peek(56320))
20 print "{clear}"
30 if j1=-255 then print "j1   ";
40 if j2=-127 then print "j2   ";
50 if (j1 and 1) then print "j1 ^ ";
60 if (j2 and 1) then print "j2 ^ ";
70 if (j1 and 2) then print "j1 v ";
80 if (j2 and 2) then print "j2 v ";
90 if (j1 and 4) then print "j1 {arrow left} ";
100 if (j2 and 4) then print "j2 {arrow left} ";
110 if (j1 and 8) then print "j1 > ";
120 if (j2 and 8) then print "j2 > ";
130 if (j1 and 16)then print "j1 Q ";
140 if (j2 and 16)then print "j2 Q ";
150 goto 10
