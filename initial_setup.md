## 🛠 Hardware Used

- **SBC:** Raspberry Pi 5 (4GB)
- **Display:** Waveshare 7" DSI (800x480) Touchscreen
- **Cables & Connectors:** Official Raspberry Pi DSI cable

## 🔧 Setup Instructions

### 1️⃣ Configure the config.txt:

#### Connect to Raspberry Pi through SSH via PuTTY
1. Install [PuTTY](https://www.putty.org) on your desktop.
2. Before getting IP address, make sure to power on Raspberry Pi.
3. Get Angry IP Scanner to find your Pi's IP address.
4. Enter **'Username'** and **'Password'** to enter the SSH terminal.

#### Enable DSI Display:

1. Open terminal in PuTTY:
##### *For Raspberry Pi 5 Only*:
   ```bash
   sudo nano /boot/firmware/config.txt
   ```
##### *For Raspberry Pi other than 5*:
   ```bash
   sudo nano /boot/config.txt
   ```
2. Add or modify the following lines:
   ```ini
   dtoverlay=vc4-kms-v3d
   #For connecting in DSI1 uncomment next line 
   dtoverlay=vc4-kms-dsi-7inch
   #For connecting in DSI0 uncomment next line
   #dtoverlay=vc4-kms-dsi-7inch,dsi0
   ```
3. Save and exit (`CTRL+X`, then `Y` and `Enter`).
4. Reboot the system:
   ```bash
   sudo reboot
   ```

### 2️⃣ Connect the Hardware:

1. Attach the **Waveshare 7" DSI screen** to the **Raspberry Pi** using the **DSI ribbon cable**.
2. Ensure the screen is powered via the Raspberry Pi by connecting the **5V** and **GND** to Raspberry Pi's GPIO.
3. If not sure what pins to connect, visit [pinout](https://pinout.xyz) for reference.

### 3️⃣ Touchscreen Calibration (Completely Optional):

For better touchscreen accuracy, install the **xinput** calibration tool:

```bash
sudo apt install xinput-calibrator
```

## 📝 NOTE:
**DO NOT TOUCH THE SCREEN** while the Raspberry Pi is booting via the DSI display. It will prevent the touchscreen feature to work properly. 


## 📸 Screenshots

*(Add images of your setup here!)*


---

