# motor-control
import RPi.GPIO as GPIO
import time

# Motor control pins
MOTOR_PIN = 18

# GPIO setup
GPIO.setmode(GPIO.BCM)
GPIO.setup(MOTOR_PIN, GPIO.OUT)

# Function to start the motor
def start_motor(duration=5):
    print("🔧 Starting motor...")
    GPIO.output(MOTOR_PIN, GPIO.HIGH)
    time.sleep(duration)
    GPIO.output(MOTOR_PIN, GPIO.LOW)
    print("🛑 Motor stopped.")

# Run the motor for 5 seconds
if __name__ == "__main__":
    try:
        start_motor()
    finally:
        GPIO.cleanup()
        print("GPIO cleaned up.")
