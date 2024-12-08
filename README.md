# Get Current User in Terminal

This Arduino sketch utilizes the DigiKeyboard library to open a terminal and execute a simple command to display the current user.

## Code

```cpp
#include <DigiKeyboard.h>

void setup() {
  pinMode(1, OUTPUT); // LED on Model A

  // Initialize DigiKeyboard
  DigiKeyboard.update();
  DigiKeyboard.delay(3000);

  DigiKeyboard.sendKeyStroke(0, MOD_GUI_LEFT); // Open the terminal
  DigiKeyboard.delay(5000);
  
  DigiKeyboard.print("terminal"); // Type "terminal"
  DigiKeyboard.delay(5000);

  DigiKeyboard.sendKeyStroke(KEY_ENTER); // Press Enter
  DigiKeyboard.delay(5000);

  DigiKeyboard.print("whoami"); // Execute "whoami" command
  
  digitalWrite(1, HIGH); // Turn on LED when program finishes
}

void loop() {
  // No loop needed
}
