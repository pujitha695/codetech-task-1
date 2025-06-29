# codetech-task-1
COMPANY: CODTECH IT SOLUTIONS

NAME: KENGUVA PUJITHA

INTERN ID:CT04DF1654

DOMAIN: Embedded Systems

DURATION: 4 WEEKS

MENTOR: Neela Santhosh Kumar 

DESCRIPTION:
The Push Button Counter is a simple embedded systems project where a digital counter increases each time a button is pressed. It uses a microcontroller like Arduino to read the push button input and display the count on an LCD or OLED screen. A pull-down resistor is used to ensure stable input readings. Debouncing is implemented in code to prevent false triggering. This project helps in understanding digital input, output display interfacing, and basic programming logic. It is commonly used in applications like people counters, product counting systems, and digital scoreboards. It’s an ideal beginner-level project in electronics.

CIRCUIT DIAGRAM:
![file_00000000e9cc622fbb7281ff79c66694](https://github.com/user-attachments/assets/473400d1-8b28-4a29-8c3b-bd1456fd8e52)

CODE:
#include <LiquidCrystal.h>

// LCD pins: RS, E, D4, D5, D6, D7
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);

const int buttonPin = 2;
int counter = 0;
int buttonState = 0;
int lastButtonState = 0;

void setup() {
  pinMode(buttonPin, INPUT);
  lcd.begin(16, 2);
  lcd.print("Counter: ");
  lcd.setCursor(0, 1);
  lcd.print(counter);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH && lastButtonState == LOW) {
    counter++;
    lcd.setCursor(0, 1);
    lcd.print("                "); // Clear line
    lcd.setCursor(0, 1);
    lcd.print(counter);
    delay(200);  // Debounce delay
  }

  lastButtonState = buttonState;
}

OUTPUT:

![file_000000008eb061f69ee4894b58bdc485 (1)](https://github.com/user-attachments/assets/29eb0981-595d-46d9-8dc8-d7cbe540ce5a)

WORKING DEMO:

https://youtu.be/hIQgd8ydFac?si=n8fogsGnqSqnytBo

