---
up: "[[Sistemas Embebidos]]"
---

```python
from gpiozero import LED, Button
from time import sleep

# Define LEDs
red_led = LED(22)
yellow_led = LED(27)
green_led = LED(17)

# Define Push Button
button = Button(4)

# Variables to track button press
shorten_green = False

# Function to handle button press
def shorten_green_time():
    if green_led.is_lit:
        shorten_green = True

# Link the button press to the function
button.when_pressed = shorten_green_time

while True:
    # Red light for 3 seconds
    red_duration = 3 + (1.5 if shorten_green else 0)  # Extend red if green was shortened
    red_led.on()
    yellow_led.off()
    green_led.off()
    sleep(red_duration)

    # Reset shorten_green flag after red light
    shorten_green = False

    # Green light for 3 seconds (or 1.5 seconds if shortened)
    green_duration = 1.5 if shorten_green else 3
    red_led.off()
    yellow_led.off()
    green_led.on()
    sleep(green_duration)

    # Green light blinking for 2 seconds (500ms on/off)
    for _ in range(4):
        green_led.toggle()
        sleep(0.5)

    # Yellow light for 1 second
    red_led.off()
    yellow_led.on()
    green_led.off()
    sleep(1)

    # Back to red (loop continues)

```