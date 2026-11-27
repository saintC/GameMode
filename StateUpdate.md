# 11/26/2026
# GM1 Firmware Version vU1
UI Overhaul, Rendering (Proper GPU & CPU & RAM utilisation, Drawing, Etc.)
edk2 + edk2-libc intergated
Controller Support Added (Xbox Controllers as of now)
Installer & Bootable Soon
GTA:SA Getting Ported for the GameMode 1 after everything is done, will analyse how rendering & drawing works (unlikely for now)
Sound & Network & Storage Services will be added

# 11/27/2026
# GM1 Firmware Version vU1 (Bootable)
roughly 6 more test passes to get a working controller driven ui, then several build phases before getting started on a gta sa port

tests on hardware (usb boot):

1. controller input: confirm Pad: A (0x0010) style lines print when you press buttons (GIP, just built, untested)
2. Keyboard/mouse over USB: HID is not in the EDK2 shell yet, so this needs porting and a test
3. Display: confirm the 2560x1440 mode holds, and that a second monitor stays inactive
4. Graphics output: draw a solid-color frame through GOP (no text) to confirm we can paint pixels
5. Menu draw: a static boot-menu screen with a moving selection cursor driven by the controller
6. Menu actions: select and launch an item and return to the menu
build work before the UI is usable:

Port the boot-menu layer (text, rectangles, and a basic font) onto GOP
Connect the input layer to menu navigation (D-pad, A/B, and the HID path)
Add the power-off / reboot / return-to-firmware items
build work before starting gta sa porting:

software renderer target, starting with a frame buffer and triangle rasterizer
re3 integration: the game needs its file loader, asset path, and platform layer swapped for the UEFI environment
