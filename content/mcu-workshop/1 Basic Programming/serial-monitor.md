---
title: Serial Monitor
---
Using serial over USB to print messages from the Pico.
# Components
No additional components.
# Exercise
You can use a USB serial monitor program to trace output logs from the Pico. This is useful to print out some basic debugging information or to get some external input.

VSCode has a built-in serial monitor, you can find it as one of the tabs in the "Terminal":
![[VSCode Serial Monitor.png]]

Other serial monitor programs are:
- [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) (Windows)
- `minicom` (Linux, macOS)

Build and upload the `serial-monitor` program, connect the serial port and then reset the Pico. You should see a message appear in the log.

## Serial Input
The serial monitor can also be used to send inputs to the Pico over USB. You can do this using the `gets()` function.

Here's an example of how to receive a string using this function:
```C++
// Create an empty string.
char string[21] = {'\0'};  

// Use fgets to receive up to 20 chars into the string.
fgets(string, 20, stdin);

// Print the string back again.
printf("Received string: %s\n", string);
```

> [!Exercise]
> Can you make a **short quiz** using the serial input and output?
>
> Print a message to ask a question, and then when the user gives an answer, print out "Correct" or "Incorrect".
> 
> *Hint: use the [`strcmp`](https://en.cppreference.com/w/c/string/byte/strcmp) function to check if strings are equal.* 

