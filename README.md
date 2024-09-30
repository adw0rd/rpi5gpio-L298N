# rpi5gpio-L298N

* Raspbian GNU/Linux 12
* Linux raspberrypi 6.6.31+rpt-rpi-v8
* Raspberry Pi 5 Model B Rev 1.0

![image](https://github.com/user-attachments/assets/0092d7b8-ac03-459e-b17f-66e4d8a19a12)

Example with gpiozero for `Raspberry Pi 5`:

```python
from time import sleep
from gpiozero import Robot, Motor, OutputDevice

robot = Robot(left=Motor(5, 6), right=Motor(13, 19))
device = OutputDevice(26)

device.on() # .off()

for i in range(5):
    robot.forward()
    sleep(1)
    robot.backward()
    sleep(1)
    robot.left()
    sleep(1)
    robot.right()
    sleep(1)
    print("iter", i)

```

Deps:

```
$ dpkg --get-selections | grep -i gpio
gpiod                                           install
libgpiod2:armhf                                 install
liblgpio1:armhf                                 install
libpigpio-dev                                   install
libpigpio1                                      install
libpigpiod-if-dev                               install
libpigpiod-if1                                  install
libpigpiod-if2-1                                install
pigpio                                          install
pigpio-tools                                    install
pigpiod                                         install
python3-gpiozero                                install
python3-lgpio                                   install
python3-libgpiod:armhf                          install
python3-pigpio                                  install
python3-rpi.gpio                                install
raspi-gpio                                      install
rpi.gpio-common:armhf                           install
```
