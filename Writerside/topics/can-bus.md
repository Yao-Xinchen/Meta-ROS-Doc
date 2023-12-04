# CAN Bus

## Prerequisites

### Busybox

Busybox is a set of Unix utilities. It is used to execute the `devmem` command.
It can modify the data in registers.

In linux, devices are represented as files.
The `devmem` command can modify the data in the file.
Specifically, it is used to enable the pins of the CAN bus on Orin Nano.

To install busybox, run the following command:

```bash
sudo apt-get install busybox
```

### Hardware

We need `CAN_H` and `CAN_L` to communicate with the motors.

Depending on different carrier boards, the hardware requirements are different.

<tabs>
    <tab title="Original Board">
        <img src="original_board_pin.png" alt="Orginal Board" width="600"/>
        The pins on the original board are CAN_TX and CAN_RX.
        However, CAN_H and CAN_RX are what we need.
        Therefore, a CAN transceiver is required.
    </tab>
    <tab title="DM Board">
        <img src="dm_board_pin.png" alt="DM Board" width="500"/>
        The pins on the DM board are `CAN_H` and `CAN_L`.
        <note>
            <p>
                Note that `CAN_H` is on the left and `CAN_L` is on the right.
            </p>
            <p>
                This is different from the order on DJI boards and motors.
            </p>
        </note>
    </tab>
</tabs>

> Make sure there is at least one **terminator resistor** on the CAN bus.
> 
> Otherwise, CAN frame will not be transmitted correctly, which would lead the computer to keep transmitting the same frame.
{style="warning"}

## Enable CAN Bus

To enable CAN bus, run the following commands:

```bash
sudo busybox devmem 0x0c303018 w 0xc458
sudo busybox devmem 0x0c303010 w 0xc400
sudo modprobe can
sudo modprobe can_raw
sudo modprobe mttcan
ip link set can0 up type can bitrate 1000000 dbitrate 1000000 berr-reporting on fd on
```

## Utilities

To manually use the CAN bus, install `can-utils`:

```bash
sudo apt-get install can-utils
```

### Send

Use `cansend`. An example:

```bash
cansend can0 123#abcdabcd
```

In this example, `123` is the ID of the message, and `abcdabcd` is the data.

### Receive

Use `candump`. An example:

```bash
candump can0
```

To put it in the background, add `&` at the end.

## Debug

We can use loopback to test the CAN bus.

```bash
ip link set can0 type can bitrate 1000000 loopback on
ip link set can0 up
candump can0 &
cansend can0 123#abcdabcd
```

If the loopback is successful, you will see:

```bash
can0 123 [4] AB CD AB CD
can0 123 [4] AB CD AB CD
```