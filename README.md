# Prebuild nRF52840 dongle BLE HCI UART Firmware

This repository contains prebuilt Zephyr [BLE HCI <-> UART firmware](https://docs.zephyrproject.org/latest/samples/bluetooth/hci_uart/README.html) for an [nRF52840 dongle](https://www.nordicsemi.com/Products/Development-hardware/nRF52840-Dongle).

## Flashing the firmware

1. Install `nrfutil`. [Follow the Instructions here](https://docs.nordicsemi.com/bundle/nrfutil/page/guides/installing.html#prerequisites).

2. Install `nrf5sdk-tools`: 
```
nrfutil install nrf5sdk-tools
```

3. Download the `nrf52840dongle_bluetooth_hci_uart.zip` from the [Releases](https://github.com/timrid/ble-dongle-firmware/releases).

4. Reset the board into the Nordic bootloader by pressing the RESET button.

The push button is on the far side of the board from the USB connector. Note that the button does not face up. You will have to push it from the outside in, towards the USB connector:

![nRF52840 Dongle](img/nRF52840_dongle_press_reset.png)

The red LED should start a fade pattern, signalling the bootloader is running.

5. Find the serial port of the dongle:

E.g. on macOS: 
```
ls /dev/tty.usbmodem*
```

6. Flash the firmware: 
```
nrfutil nrf5sdk-tools dfu usb-serial -pkg nrf52840dongle_bluetooth_hci_uart.zip -p YOUR-PORT-NUMBER
```