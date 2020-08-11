# Color formatter
## About
This library allows you to easily format your strings in two ways:
- **Variable formatting** 
- **Color formatting**

Variable formatting allows you to insert your variables inside a string, and color formatting allows you to change the color of the outputted message.
## How to use
### Variable formatting
To use variable formatting you simply put **%v** at the place where you want to insert the variable. Supports most types.
### Color formatting
To use color formatting inside your string you do **{color:desired_color=text}**, you can also insert **%v** there. Everything else besides these **{...}** will get gray color.
## Features
Color formatter library currently supports these functions:
### console::colorset
Sets current console color to the specified color.
```cpp
void console::colorset(int color);
```
### console::colorwrite
Writes a string to a console with specified color.
```cpp
void console::colorwrite(int color, std::string str);
```
### console::colorformat
Formats a message with optional colors.
```cpp
void console::colorformat(std::string str, vars...);
```
### Colors map
You can see and use each and every available colors in the colors map. To get an integer corresponding to that color:
```cpp
int color = console::colors["purple"]; // 5
```
## Examples
### a + b = c
```cpp
int a = 10, b = 20, c = a + b;
console::colorformat("{color:light_blue=%v} + {color:light_blue=%v} = {color:light_green=%v}\n", a, b, c);
```
### Warn
```cpp
console::colorformat("{color:orange=[WARN]} %v\n", "warn message here...");
```
### Hello, world!
```cpp
console::colorformat("{color:pink=Hello}, {color:cyan=world}!\n");
```
### Number Pi
```cpp
console::colorformat("Pi: {color:light_red=%v}\n", 3.141593f);
```