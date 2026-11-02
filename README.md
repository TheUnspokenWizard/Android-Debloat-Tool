Android Debloat Tool
A Windows desktop utility for managing installed Android applications through Android Debug Bridge (ADB). It is designed to let users review installed packages and uninstall selected apps for Android's primary user without requiring root access.
Important: No-root debloating normally removes an app for Android user 0; it does not physically erase protected system APKs from the system partition.

Download
Get the latest packaged Windows build from the repository's Releases page.
1. Download the latest AndroidDebloatTool.zip.
2. Extract the ZIP file.
3. Open the extracted AndroidDebloatTool folder.
4. Run AndroidDebloatTool.exe.
Keep the complete extracted folder together. The _internal directory contains runtime files and ADB components required by the application. Do not run the EXE from inside the ZIP preview.
Features
- Detects Android devices connected over USB using ADB.
- Scans installed Android packages and identifies user apps and system apps.
- Displays packages for individual selection, with search and bulk-selection controls.
- Attempts to uninstall selected packages for Android user 0.
- Shows per-package results and live progress.
- Offers a reboot action after a successful debloat operation.
- Includes About and Donate menus, with BTC and ETH addresses and QR images.
Requirements
- Windows 10 or Windows 11.
- An Android device and a USB data cable.
- USB debugging enabled on the Android device.
- The device must authorize the computer's USB debugging RSA prompt.
Root access is not required.
Getting started
1. Enable Developer options
On your Android device:
1. Open Settings → About phone.
2. Find Build number (the exact location varies by manufacturer).
3. Tap Build number seven times, until Developer options are enabled.
4. Return to Settings and open Developer options.
5. Enable USB debugging.
2. Connect and authorize the device
1. Start Android Debloat Tool on Windows.
2. Connect the phone using a USB data cable.
3. Unlock the phone.
4. Accept the Allow USB debugging? prompt and, if appropriate for your own PC, select Always allow from this computer.
5. In the application, refresh the device list and select the connected device.
3. Scan and select apps
1. Click Scan apps.
2. Wait for the installed package list to load.
3. Search for a package or browse the list.
4. Select only packages you understand and intend to remove.
5. Review the selection carefully before continuing.
4. Debloat and reboot
1. Click Debloat selected apps.
2. Read the confirmation prompt and confirm only if you are sure.
3. Follow the live progress and per-package results.
4. When the operation finishes, use Reboot device if a reboot is needed.
What does “without root” mean?
The tool uses the Android package manager through ADB. The uninstall operation is performed for the primary Android user, typically with a command equivalent to:
adb shell pm uninstall --user 0 PACKAGE_NAME
This is different from deleting an APK from the protected system partition. Depending on the device and Android version:
- The app may remain in the system image.
- A factory reset, firmware update, or system update may restore the app.
- Some packages cannot be uninstalled because the manufacturer or Android restricts them.
- Removing a package that another feature depends on may cause features to stop working.
Safety notice
Debloating can break device features. Removing the wrong package may affect calls, messaging, settings, notifications, biometrics, camera functions, launcher behavior, updates, or other manufacturer-specific features.
- Review every package name before removing it.
- Do not remove packages you cannot identify.
- Do not attempt to remove Android core, Settings, System UI, telephony, package installer, permission controller, or Google service components unless you fully understand the consequences.
- The application's protected-package checks are conservative safeguards, not a complete safety guarantee for every manufacturer or model.
- Back up important data before making system changes.
- You are responsible for the packages you choose to uninstall.
Some removals may fail because of Android, OEM, carrier, or enterprise-device restrictions. A failed removal does not necessarily indicate a problem with the tool.
Restore an app
If an app was uninstalled for user 0 and the system image still contains it, it may be possible to restore it using ADB:
adb shell cmd package install-existing PACKAGE_NAME
Replace PACKAGE_NAME with the exact package name. Restoration is not guaranteed for every app or device.
Troubleshooting
Problem	What to try
No device detected	Check the USB cable supports data, try another USB port, and refresh the device list.
Device shows as unauthorized	Unlock the phone and accept the USB debugging RSA prompt.
Multiple devices connected	Select the correct device in the application before scanning.
Scan fails	Confirm USB debugging is enabled and the device is authorized. Reconnect and try again.
App uninstall fails	The package may be protected, required by the OEM, or restricted by device policy.
Device features stop working	Restore the relevant package if possible, or use the manufacturer's supported recovery/reset process.


Repository contents
The distributed AndroidDebloatTool.zip is a packaged Windows application. It contains the executable and its bundled runtime/dependency files, including ADB components and the BTC/ETH QR images.

This ZIP is a binary distribution, not the Python source-code project. If you intend to publish the source code, add the .py source files and build instructions separately.
Donate
If you find the project useful, you can support future updates:
- BTC: bc1qg5twsmpsqvq705hr70psfgt5xdmwy2p8k9d
- ETH: 0xbf6D22CDb9105B71e4AC2877c0BB0E086a6Ed0c4
Please verify the displayed address carefully before sending any cryptocurrency. Transactions are irreversible.
About
Developed by: Unspoken Wizard
Contact: debloatware@proton.me
Disclaimer
This project is provided "as is", without warranty of any kind. The developer is not responsible for data loss, device malfunction, boot issues, or other damage resulting from package removal or use of this software. Use it only on devices you own or are authorized to manage.
