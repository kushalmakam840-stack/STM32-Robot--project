## Work Completed
- Configured **TIM2 Channel 1 (TIM2_CH1)** for PWM generation on PA0 of the STM32F401RBT6.
- Configured the timer using Prescaler (PSC) = 83 and Auto-Reload Register (ARR) = 99.
- Set the PWM compare value (CCR1) to 35, then tested a value of 50 to explore duty-cycle control.
- Configured PC0 and PC1 as GPIO outputs for the TB6612FNG motor direction inputs.
- Connected the STM32 PWM output to PWMA and tested the N20 6 V DC gear motor through the TB6612FNG.
- Observed the motor rotating during initial testing and later experiencing intermittent stopping and twitching.

## Understanding
- PWM frequency depends on the timer clock, prescaler, and auto-reload value.
- The CCR1 value controls PWM duty cycle.
- PWM is used to control motor drive and influence speed.
- The TB6612FNG requires direction inputs, a standby-enable signal, motor power, and a common ground reference.

## Issues to Investigate
- Motor starts briefly but then stops or twitches.
- Verify common ground between the STM32, driver, and motor supply.
- Check motor supply voltage under load, wiring, and driver input states.

**Platform:** STM32F401RBT6 | STM32CubeIDE | TB6612FNG | N20 6 V gear motor
