# Samsung Temp Root Guide

[English ver](https://github.com/mydaudat1/Samsung-Temp-Root-Guide/blob/main/README.md)

[Bản tiếng Việt](https://github.com/mydaudat1/Samsung-Temp-Root-Guide/blob/main/README-vi.md)

Temp root on devices running OneUI 8+ has been quite popular lately, and as someone who has tried it and bricked a device, I'll share some tips with you.
## Choosing an exploit app:
- **Root My Galaxy**: The classic, respectable, but it supports very few devices.
- **Root My Galaxy Next**: The best fork of the original RMG. It adds DirtyFlag support and many payloads for various devices. Arguably the most active repo of the bunch. (Rooting via DirtyFlag supports upstream KernelSU.) However, some features won't work.
- **Root My Galaxy Forks (device-specific)**: RMG forks that focus only on certain device models.
- **DFRoot/DirtyFlag**: Uses DirtyFlag to exploit. Fewer features, but high quality. It does not support upstream KernelSU (sad).
## Root managers:
They're all the same.
## IMPORTANT: Brick Prevention & Recovery Tips
## 1: D2 Error:
- **Explanation**: If you have a lock screen password (PIN) set on the device, Download Mode will be blocked and you won't be able to enter it when the device is bricked.
- **Solution**: Don't set a PIN.
## 2: Security Error:
- **Explanation**: Temp root doesn't affect the bootloader, so if you flash anything that touches the bootloader, you'll get this error. Luckily, Knox won't be tripped.
- **Solution**: Flash the stock ROM.
## 3: Bootloop:
- **Explanation**: The module you flashed is faulty, or the superuser just did something wrong.
- **Solution**: Flash the stock ROM.
## 4: Data loss:
- **Explanation**: Data stored locally on your device will be lost when it bricks.
- **Solution**: Back up before you do anything.
## Error severity ranking:
|Rank|D2|Security Error|Bootloop|Data Lost|
|:---:|:---:|:---:|:---:|:---:|
|Extremely dangerous|✅️ (if bricked)||||
|Dangerous||✅️|✅️|||
|Normal|✅️||
|Annoying||||✅️|
## Unbrick guide
## On Android:
**1: Preparation:**
- A reliable USB cable that can transfer data.
- An Android phone.
- The device already in Download Mode.
- The device's stock ROM.
- Brokkr

**Instructions**:
- **Step 1:** Extract the stock ROM file.
- **Step 2:** Open Brokkr and enable Auto Reboot.
- **Step 3:** In the AP slot, select the .tar file whose first two letters match the slot name (e.g., AP_XM510...)
- **Step 4:** Do the same for the BL, CP, and CSC slots (Wi-Fi-only devices won't have a CP file; if there isn't one, skip the CP slot).
- **Step 5:** Skip the USERDATA slot.
- **Step 6:** Connect the USB cable to the device you're unbricking and start flashing (keep an eye on the device so it doesn't shut off by itself, which would cause the flash to fail).
## On PC
- A reliable USB cable that can transfer data.
- A Windows PC.
- The device already in Download Mode.
- The device's stock ROM.
- Odin.
## Instructions:
- **Step 1:** Extract the stock ROM file.
- **Step 2:** Open Odin and enable Auto Reboot.
- **Step 3:** In the AP slot, select the .tar file whose first two letters match the slot name (e.g., AP_XM510...)
- **Step 4:** Do the same for the BL, CP, and CSC slots (Wi-Fi-only devices won't have a CP file; if there isn't one, skip the CP slot).
- **Step 5:** Skip the USERDATA slot.
- **Step 6:** Connect the USB cable to the device you're unbricking and start flashing.

**Important note**: Some devices use a multi-CSC (mixed) firmware (usually OXX or OLM). When you install this kind of CSC, you may need to do more region setup afterward. (e.g., XXV – Vietnam falls under OLM – Multi-CSC)
## How to download the stock ROM:
- **Step 1**: Copy the string after the second dot in the Build Number field (Settings -> About this Phone -> Software Information).
- **Step 2**: Go to [SamFW](https://samfw.com/)
- **Step 3**: In the "Enter device name or model code" box, paste the string you just copied.
- **Step 4**: Select the CSC.
- **Step 5**: Download.

Note: If your device is stuck on the Download Mode screen and you can't boot into the OS, the **only way** is to find the PRODUCT NAME and work out the CSC from memory. That's why you should always have the stock ROM ready before you do anything.

**How to find your CSC:**
In the Service provider software version field (Settings -> About this Phone -> Software Information), the 3 characters after your model name are the CSC. (e.g., in SAOMC_SM-G996B_OXM_XXV_15_0008 XXV/XXV,XXV/XXV, SM-G996B is the model name and OXM is the CSC code you're looking for.)
## Keywords to avoid
- Direct Install
- Anti-bootloop
- Hide
- Bootloader
- Kernel
- SUFS modules
## Warranty issues
If your device gets a Security Error/bootloop but is still under warranty, make sure these entries in Download Mode read as follows:
- KG STATUS: PRENORMAL (00) (or CHECKING)
- WARRANTY VOID: 0x0 (0x0)

If these lines on your device don't match, it's very likely your device has been Knox-tripped and warranty service will be refused.

Once the Knox eFuse is blown (Knox trip), the **only** way to restore it is to **replace the entire mainboard**.
## Resources
- Stock ROM: [SamFW](https://samfw.com/)
- Brokkr: [GitHub](https://github.com/Gabriel2392/brokkr-flash)
- Odin: [SamFW blog](https://samfw.com/blog/download-odin-all-version)
- FRP Remove (paid): [SamFW tool service](https://samfw.com/frp)
## Bonus
If your device has a D2 Error, there are a few more options: (untested)
## Fenrir:
**Fenrir** is an unbricking tool for Samsung technicians. You need a Samsung technician account to use it.

**How to enter**:

On the D2 screen:
- **Hold throughout**: the power button
- **Step 1**: Press Volume Up 8 times.
- **Step 2**: Press Volume Down 5 times.
- **Step 3**: Press Volume Up 9 times.

Once the QR code appears:
- **Step 1**: Take a photo of it.
- **Step 2**: Transfer the photo to a PC.
- **Step 3**: Import the photo into Fenrir to get the code (8 digits).
- **Step 4**: Press Volume Up and Volume Down to move to the digit you need to enter. Press the power button to confirm.
- **Step 5**: Move to the "Done" line and press the power button to confirm.

## Good luck!
(Find images in /image)

