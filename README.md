In this experiment, I programmed and tested GPIO-based input and output control on the TI TMS320F28379D Delfino DSP using Code Composer Studio (CCS12). The goal was to drive on-board LEDs (LD9 and LD10) as outputs and use push buttons (PB1–PB3) as inputs for user interaction through the DSP’s GPIO module.

I started configuring GPIO registers for LED control. GPIO41 and GPIO42 were set as output pins to drive LD10 and LD9, respectively. Using the GPBMUX1, GPBGMUX1, and GPBDIR registers, I defined pin functionality and direction. The LEDs were toggled in synchronization with the seconds counter of the digital clock developed in the previous lab, creating a visible blinking pattern.

Next, I initialized GPIO33 as an input to read signals from push button PB1, enabling clock reset functionality when the button was pressed. The GPBINV register was configured to invert the logic for active-low button operation. This allowed the system to detect button presses and reset the time variables in real time.

In the second part of the lab, I wrote a new program that adjusted the LED blinking rate based on the state of push buttons PB1, PB2, and PB3. Each button triggered a different blinking frequency (0.1 s, 0.5 s, and 1 s) while maintaining a 50% duty cycle for the LED.

Throughout the experiment, I observed GPIO behavior using the watch window, modified delay variables dynamically, and verified the timing response. I also analyzed differences between initializing LEDs with GPxDAT and GPxSET registers, which affected their default logic state and toggling behavior.

This lab strengthened my understanding of GPIO configuration, input/output interfacing, debouncing logic, and real-time embedded control using the TI DSP platform.
