# Prebuild nRF52840 dongle BLE HCI UART Firmware

This repository contains prebuilt BLE HCI <-> UART firmware for an [nRF52840 dongle](https://www.nordicsemi.com/Products/Development-hardware/nRF52840-Dongle).

## Flashing the firmware

1. Install `nrfutil`. [Follow the Instructions here](https://docs.nordicsemi.com/bundle/nrfutil/page/guides/installing.html#prerequisites).

2. Install `nrf5sdk-tools`: 
```
nrfutil install nrf5sdk-tools
```

3. Download the `nrf52840dongle_bluetooth_hci_uart.zip`

4. Attach the nRF52840 Dongle

2. Find the serial port of the dongle:

E.g. on macOS: 
```
ls /dev/tty.usbmodem*
```

4. Flash the firmware: 
```
nrfutil nrf5sdk-tools dfu usb-serial -pkg nrf52840dongle_hci_uart.zip -p YOUR-PORT-NUMBER``