## Cameras
Dual camera inputs on cam1 and cam0 lines.

### config.txt example:
# Disable auto-detect if you are forcing manual overlays
camera_auto_detect=0

# Define camera on Port 0
dtoverlay=imx708,cam0
# Define camera on Port 1
dtoverlay=imx708,cam1

## Stereo Microphone
Dual/stereo audio inputs on left and right edges of board.
MMICT390200012, converted from PDM to PCM.

### config.txt example:
dtoverlay=googlevoicehat-soundcard

## IMU
Bosh BNO055 9 axis IMU
UART channel 5

### config.txt example:
dtoverlay=uart5

## Fuel Gauge
MAX17048G+ smart battery fuel gauge.

# Enable I2C-3 for Fuel Gauge
dtoverlay=i2c3,pins_2_3

## GPS

### config.txt example:
dtoverlay=uart4

GPS UART4 connection seems to interfere with booting.

Fix:

Edit
/boot/firmware/cmdline.txt

The Edit:

    Find: A section of text looking like console=serial0,115200 (or console=ttyAMA0,115200).

    Action: Delete that specific section.

    Keep: Everything else (like root=..., console=tty1, fsck...).

Ensure cmdline.txt remains one single line of text. Do not add line breaks or newlines.


## All required configs (untested)

camera_auto_detect=0
dtoverlay=imx708,cam0
dtoverlay=imx708,cam1
dtoverlay=googlevoicehat-soundcard
dtoverlay=uart5
dtoverlay=i2c3,pins_2_3

