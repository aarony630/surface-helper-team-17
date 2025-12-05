from machine import Pin, PWM
import time

# ========= Motor Driver A (Motors A1 & A2) =========
A1_IN1 = Pin(6, Pin.OUT)
A1_IN2 = Pin(7, Pin.OUT)
A1_EN  = PWM(Pin(8))

A2_IN1 = Pin(4, Pin.OUT)
A2_IN2 = Pin(3, Pin.OUT)
A2_EN  = PWM(Pin(2))

# ========= Motor Driver B (Motors B1 & B2) =========
B1_IN1 = Pin(10, Pin.OUT)
B1_IN2 = Pin(11, Pin.OUT)   
B1_EN  = PWM(Pin(12))

B2_IN1 = Pin(13, Pin.OUT)
B2_IN2 = Pin(14, Pin.OUT)
B2_EN  = PWM(Pin(15))

# ========= PWM frequency =========
for pwm in (A1_EN, A2_EN, B1_EN, B2_EN):
    pwm.freq(1000)

# ========= Set speed (0–65535) =========
speed = 50000  # full speed = 65535

for pwm in (A1_EN, A2_EN, B1_EN, B2_EN):
    pwm.duty_u16(speed)


# ========= Movement Functions =========
def forward():
    # Motor A1
    A1_IN1.high()
    A1_IN2.low()

    # Motor A2
    A2_IN1.high()
    A2_IN2.low()

    # Motor B1
    B1_IN1.high()
    B1_IN2.low()

    # Motor B2
    B2_IN1.high()
    B2_IN2.low()


def stop():
    A1_IN1.low(); A1_IN2.low()
    A2_IN1.low(); A2_IN2.low()
    B1_IN1.low(); B1_IN2.low()
    B2_IN1.low(); B2_IN2.low()


# ========= Main Loop =========
while True:
    print("Forward (speed =", speed, ")")
    forward()
    time.sleep(5)

    print("Stop")
    stop()
    time.sleep(2)


