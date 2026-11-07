# Lesson 6 Exercise 1: ADC sample

This project is built for the **ESP32-S3-DevKitC** using the ESP32-S3
PROCPU target (`esp32s3_devkitc/esp32s3/procpu`).

## Sample description

The sample demonstrates how to use Zephyr's ADC API to:

- configure ADC channel 0 from the devicetree;
- read a raw ADC value once per second; and
- convert the reading to millivolts when the board supports the conversion.

The ADC configuration is provided by
`boards/esp32s3_devkitc.overlay`.

## Build

Run the following command from the `zephyrproject` directory:

```sh
west build -b esp32s3_devkitc/esp32s3/procpu \
	../ncs-inter/l6/l6_e1_sol/ \
	-d ../ncs-inter/l6/l6_e1_sol/build \
	-p always \
	-- -DEXTRA_DTC_OVERLAY_FILE="$PWD/../ncs-inter/l6/l6_e1_sol/boards/esp32s3_devkitc.overlay"
```

After flashing and starting the application, ADC readings are printed to the
Zephyr log once per second.

Run the following command from the `zephyrproject` directory to flash the binary:
```sh

west flash -d ../ncs-inter/l6/l6_e1_sol/build/

```

Run the following command from the `zephyrproject` directory to monitor the application:

```sh

python3 -m serial.tools.miniterm "<PORT>" 115200 

```
Add device like following

```sh

python3 -m serial.tools.miniterm "/dev/ttyACM0" 115200 

```