# Capacitor Controller

## Intro

There is one super capacitor on each vehicle.

According to the game rules, the power of chassis is limited.
The power provided by the battery is not enough to accelerate the vehicle fast enough.
Therefore, we need to use super capacitors to provide extra power.
They store energy when the vehicle requires less power, and release energy when the vehicle requires more power.

## CAN Bus

The capacitor is connected to the CAN bus. \
Its **control ID** is `0x210` and **feedback ID** is `0x211`.

### CAN Driver

The driver is located in `<package>/include/<package>/can_driver.hpp`. \
It is used for basic CAN operations, such as sending and receiving frames. \
`can_driver.hpp` in different packages are the same.