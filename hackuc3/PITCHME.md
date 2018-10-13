# Circuit Python & Micro:bit

## HackUC III
---
## CircuitPython

* Subset of Python
* Used similarly to Arduino
* Compiled on board instead of computer
---
## Micro:bit

* Low cost development board
* Integrated electronics
---
## What You need

* Board (of some sort)
* Text editor
* [Web-based editor](https://python.microbit.org/v/1.1)
* [Mu](https://codewith.mu/) has a built in button to flash code
---
## Resources

* [micro:bit Micro Python reference](https://microbit-micropython.readthedocs.io/en/latest/index.html)
* [General Micro Python Reference](https://docs.micropython.org/en/latest/)
* [uflash](https://uflash.readthedocs.io/en/latest/) if using desktop text editor
---
## Hello World

```python
from microbit import *

display.scroll("Hello world!")
```
@[1](Import everything from microbit library)
@[3](`display.scroll()` will scroll a message across the screen)

Try modifying this to change the message
---
## Other Display Functions

* `display.show()`
* `display.clear()`
---
## General Coding

* Syntax is same as Python
* Conditional statements, while loops, for loops, lists are all available
---
## Loops

```python
while n < 5:
    display.show(str(n))
    n += 1
```

```python
for i in [image.HAPPY, image.SAD, image.CONFUSED]:
    display.show(i)
```
---
## Conditionals

```python
if n > 5:
    display.show("A")
else:
    display.show("B")
```
---
## Images

```python
from microbit import *

display.show(Image.HAPPY)
```
@[3](Will display the "happy" image)
---
## Creating Images

```python
my_image = Image("01234:"
                 "12345:"
                 "23456:"
                 "34567:"
                 "45678")

display.show(my_image)
```
---
## Buttons

* Get button state with `button_a.is_pressed()` (or button b)
* Can be converted to string with `str()`
* Button methods `.is_pressed()`, `.was_pressed()`, `.get_presses`
---
## Random

* random module is available
* Particularly useful: `random.randint()` and `random.choice()`
---
## Accelerometer

```python
from microbit import *

while True:
    reading = accelerometer.get_x()
    if reading > 20:
        display.show("R")
    elif reading < -20:
        display.show("L")
    else:
        display.show("-")
```
