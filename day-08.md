### Encoder testing

## 1. Objective

The objective was to test both N20 geared motor encoders independently, verify their counting directions, measure their approximate counts per revolution, and calculate their RPM.

## 2. Motor 1 Connections

| Encoder Wire | STM32 Connection |
|---|---|
| Green (C1) | PA6 – TIM3_CH1 |
| Yellow (C2) | PA7 – TIM3_CH2 |
| Black | 3.3V |
| Blue | GND |

Motor 1's encoder was successfully interfaced with STM32 using TIM3 Encoder Mode.

## 3. Motor 2 Connections

| Encoder Wire | STM32 Connection |
|---|---|
| Yellow (C2) | PA6 – TIM3_CH1 |
| Green (C1) | PA7 – TIM3_CH2 |
| Black | 3.3V |
| Blue | GND |

Motor 2 was tested independently using the same STM32 encoder input pins after disconnecting Motor 1's encoder.

The green and yellow encoder wires were swapped to obtain positive counts during forward rotation.

## 4. Encoder Testing Results

- Both motor encoders were tested independently.
- Forward and reverse rotation were detected.
- Positive encoder counts were obtained during forward rotation.
- RPM calculation was tested using a 500 ms sampling interval.

## 5. Encoder Count Comparison

| Parameter | Motor 1 | Motor 2 |
|---|---:|---:|
| Approximate counts per revolution | 1300 | 1424 |
| Forward rotation count direction | Positive | Positive |
| Testing status | Successful | Successful |

These values are preliminary measurements and should be verified through repeated revolutions.

## 6. RPM Calculation

RPM = (Delta Count × 60) / (Counts Per Revolution × Time in Seconds)

Sampling interval = 0.5 seconds.

**Motor 1:**

RPM1 = (Delta Count1 × 60) / (1300 × 0.5)

**Motor 2:**

RPM2 = (Delta Count2 × 60) / (1424 × 0.5)

## 7. Current Project Status

- Motor 1 encoder tested successfully.
- Motor 2 encoder tested successfully.
- Encoder direction verified for both motors.
- Approximate counts per revolution recorded.
- RPM calculation tested independently for both motors.
