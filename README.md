# My complementation about CMPEN 472

## Introduction

This document summarizes my work and accomplishments in CMPEN 472 at Penn State during Spring 2025. The course, taught by Professor Kyusun Choi, focused on low-level programming and system design using the Freescale MC9S12C128 microcontroller. More details about the course can be found on the official website: [CMPEN 472 Spring 2025](https://www.cse.psu.edu/~kxc104/class/cmpen472/25s/index.html).

Per course policy, I will not publish or distribute my code publicly.

Responding the requirement from the professor, Kyuson Choi, I will not publish my code in public.

## Simple summary about course target

CMPEN 472 provided an in-depth understanding of embedded system programming using assembly language. Through a series of progressive assignments, I gained experience in hardware-level programming, interrupt handling, real-time systems, and direct memory manipulation. All work was conducted using the CodeWarrior IDE and its Full Chip Simulator targeting the MC9S12C128, which uses the S12CPUv2 core.

## Simple record about my grade

Due to course policies, I only had access to my individual homework scores through Penn State's Canvas platform. Although information about exam and quiz scores was not published, I earned an **A** in the course and recall scoring in the **top 10** for both mid-term exams. Approximately **60 students** were enrolled in the course during Spring 2025.

## Details about my score over each homework

### Homework 1: StarFill (Memory Fill)

The first homework introduced the MC9S12C128 development environment and basic assembly programming. I was required to install CodeWarrior, read key chapters and appendices from the textbook and manuals, and simulate a basic memory fill program using the debugger. The original sample program filled 10 memory locations with asterisks; I modified it to loop 225 times and output 225 asterisks, following the assignment requirement. This task emphasized learning syntax, structure, and simulation using CodeWarrior.

My implementation featured 39 lines of code and 27 lines of comments, organized in one main loop module. I missed a few comment requirements, leading to a score of 95/100, but the functionality was correct. This assignment helped me get familiar with the IDE, debugger interface, memory layout, and assembly language syntax conventions.

### Homework 2: LED Blinking

This homework focused on learning parallel port I/O, subroutine structuring, and conditional control using switch input. I created a program to blink LED1 and LED4 alternately with a 1-second period, while using Switch 1 (SW1) to switch modes: if unpressed, it ran alternate blinking; if pressed, it displayed a sequential lighting pattern from LED4 to LED1.

I wrote 116 lines of code and 75 lines of comments, structured into three core modules: initialization, delay subroutine, and switch-based LED control. The simulation matched the assignment behavior perfectly. Detailed comments and accurate switch interpretation helped me earn a full score of 100/100.

### Homework 3: LED PWM with Timing Control

In this assignment, I implemented manual Pulse Width Modulation (PWM) to dim LED4 depending on the state of SW1. The program had to pulse LED4 with either a 5% or 25% duty cycle, cycling at 1000 Hz by adjusting ON and OFF delays using a delay10usec subroutine. The main goal was to understand how timing loops simulate PWM in software.

I developed 153 lines of code with 101 lines of comments, separated into four modules: mainloop, delay10usec, switch check logic, and LED control. My code maintained exact PWM cycles and clean modularity. The behavior was validated in the simulator and would match actual board operation, earning me a 100/100.

### Homework 4: Smooth LED Dimming with PWM

This task built upon Homework 3 to implement a smooth dimming effect for LED4. The light intensity had to increase from 0% to 100% and decrease back to 0% over 0.4 seconds, in repeated cycles. This required generating ON/OFF counters using a single brightness LEVEL variable and gradually modifying it in a loop.

My implementation spanned 202 lines, including 138 lines of comments, across five modules: dimUP, dimDN, PWM generator, delay10usec, and main control. The code achieved a full-range fade effect with clean symmetry and visual smoothness. Proper modular structure and rich documentation contributed to my perfect 100/100.

### Homework 5: Serial-Controlled LED Menu

In Homework 5, I developed a menu-based user interface through the serial terminal to allow control over individual LEDs. Commands like L1 and F1 turned LEDs on and off, while L4 and F4 triggered smooth dimming. A QUIT command exited to typewriter mode. The challenge was creating an interactive, self-explanatory system with clear feedback and error resistance.

My solution had 487 lines of code and 276 lines of comments, split into six functional modules: menu display, serial I/O, command parsing, LED control, PWM transition, and fallback mode. It was designed to be foolproof, with complete command feedback and graceful handling of invalid input. I received a perfect score of 100/100 for this assignment.

### Homework 6: Memory Viewer and Editor

This assignment required building a tool to read and write memory using commands entered through the serial terminal. The S command displayed the contents of a memory location, while W allowed the user to write 16-bit values. I implemented both hexadecimal and decimal input formats, with full validation and formatted output in binary, hex, and decimal.

I wrote 689 lines of code, with 422 lines of commentary, and divided it into eight main modules including parsers, error checking routines, number converters, and memory access logic. My program echoed back instructions, printed clear feedback, and rejected malformed input. The robustness of the interface and accurate conversions earned me a full 100/100.

### Homework 7: Calculator with Serial Input

For Homework 7, I built a simple calculator that performed integer operations (+, -, \*, /) on two positive decimal numbers with up to 4 digits. The calculator handled input echoing, output formatting, overflow detection, and invalid input rejection. It also displayed answers in the form of a+b=c.

My implementation had 632 lines, including 386 lines of comments, spread across seven modules: input handler, validator, arithmetic executor, overflow checker, and display logic. I handled various error cases like invalid characters, misplaced operators, or out-of-bound numbers. The result was a clean and responsive user interface, rewarded with a 100/100.

### Homework 8: Real-Time Clock with Command Interface

This task focused on using RTI to build a live digital clock that updates every second and accepts clock control commands like t, h, m, s, and q. The current time and commands were displayed in real-time on the terminal and 7-segment LEDs. The program maintained a single-line terminal layout and updated columns in sync with the clock.

My submission featured 761 lines of code and 412 lines of comments, across nine modules covering timekeeping, LED display, RTI handling, terminal output, and command parsing. I ensured accurate timing and intuitive user interaction. With clear separation between core logic and utilities, the program worked seamlessly and earned me 100/100.

### Homework 9: Clock + Calculator Hybrid

This assignment combined the calculator from Homework 7 and the clock from Homework 8 into a multi-tasking program. Both components ran concurrently: the clock updated every second while user inputs were parsed to either adjust the time or perform calculations. Invalid input was correctly routed to the appropriate handler and reported in the Error> column.

My code grew to 940 lines, with 530 lines of comments, and was divided into ten structured modules. I created unified handlers for display, input, and subroutines shared between the clock and calculator. The parallelism was handled gracefully using interrupts and polling. This integration challenge was met with clean design and yielded a 100/100 score.

### Homework 10: Clock + Waveform Generator

The final project introduced waveform generation using Timer OC5 interrupt at 8000 Hz, alongside the digital clock. Commands like gw, gt, gq triggered sawtooth, triangle, and square waveforms, with 2048-point outputs printed in real time. The clock remained active, and invalid commands triggered error messages.

My final program had 1,142 lines, with 688 lines of comments, organized into twelve modules: waveform logic, interrupt handlers, real-time clock, command parser, and user display. I also submitted a report analyzing the signals in MATLAB and performing FFTs on each waveform. The project was technically dense, but my modular design and precise control led to a 100/100.

### Homework 11: Analog Signal Acquisition with HCS12

This assignment extended the waveform generation system from Homework 10 by adding analog signal acquisition via the HCS12’s ADC module. The key goal was to collect 2048 analog samples at a rate of 8kHz (every 125µs) while maintaining concurrent digital clock display on the 7-segment LEDs. I implemented a new command `adc` to trigger acquisition and formatted the output to the terminal in ASCII decimal format. The collected data could be visualized using Excel or MATLAB for further signal and FFT analysis. Additional waveform commands from Homework 10 remained active, enabling direct comparisons.

My implementation contained **1,218 lines of code**, with **795 lines of comments**, structured across **thirteen modules** including Timer OC5 interrupt control, ADC input, ASCII conversion, serial communication, and waveform and clock management. The program successfully achieved precise 8kHz sampling and ASCII output with minimal latency. I also plotted various waveforms (sine, square, triangle, mixed) and analyzed their FFTs, as required. This highly technical task was completed robustly, and I earned **100/100**.

### Homework 12: Serial Port Monitor Program

The final homework involved developing a serial-port-based MONITOR system for direct memory access and program control. I implemented commands like `S`, `W`, `MD`, `LD`, `GO`, and `QUIT`, allowing users to inspect and manipulate memory via a command-line interface. For example, `S$3000` would show a memory word, and `W$3000 $126A` would write a word to memory. Additional features included block memory loading and viewing (via `LD` and `MD`), and executing code with `GO`. The system included detailed error checks and messages to handle invalid inputs gracefully.

The final program consisted of **1,396 lines of code** with **875 lines of comments**, divided into **fifteen logical modules**, including command parsing, address validation, decimal/hex converters, error protection for restricted memory areas, and the fallback `TypeWriter` terminal. I ensured extensive user feedback, robust input validation, and modular design. This system-level project consolidated everything I learned in CMPEN 472 and demonstrated my ability to design and implement a reliable embedded tool. I received **100/100** for this culminating assignment.
