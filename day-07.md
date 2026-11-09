# Day 7 – STM32 Dual Motor PWM Control

## Work Completed

Today, I successfully implemented dual DC motor control using the STM32F401RBT6 and TB6612FNG motor driver.

### 1. STM32 PWM Configuration
- Configured TIM2 Channel 1 using PA0.
- Configured TIM2 Channel 2 using PA1.
- Configured PA1 as TIM2_CH2 with Alternate Function AF1.
- Started both PWM channels using STM32 HAL.

### 2. TB6612FNG Motor Driver
- Connected and configured both motor channels.
- Configured direction control pins:
  - Motor A: PC0 and PC1.
  - Motor B: PC10 and PC11.
- Successfully tested both DC motors.

### 3. Button-Based Speed Control
Implemented button-based PWM speed control:
- First press: Both motors receive a compare value of 50.
- Second press: Both motors receive a compare value of 70.
- Repeated button presses toggle between these two values.

### 4. Problem Identified and Fixed
Initially, both motors were behaving differently even though the same PWM compare values were being used.

**Root cause:** TIM2 Channel 1 was configured in PWM Mode 1, while Channel 2 was configured in PWM Mode 2.

**Solution:** Changed Channel 2 from PWM Mode 2 to PWM Mode 1.

After correcting the configuration, both motors responded consistently to the same PWM settings.

## Current Result

Successfully achieved simultaneous control of two DC motors using STM32 TIM2 PWM channels and the TB6612FNG motor driver.

## Next Steps
- Interface both motor encoders with STM32 timers.
- Measure individual motor RPM.
- Implement independent PID speed control.
- Work towards accurate differential-drive robot movement.
