# qemu_sk_deb_install
This is a installation debian package for Savira Kotigalu (Thousand Monkeys) qemu HID usb educational device. When installed this deb package, QEMU devices will have a new USB hid device called 'usb-sk-kbd'. It is a HID device can be used as a autotype writer when attached to a virtual machine. Whenever, it is attached to a virtual machine while booting up, it creates a FIFO write end at /tmp/kotigalu directory, with corresponding process ID of the qemu. Users, can just write into text into FIFO and mount the cursor on a editor, the usb-sk-kbd starts pumping in characters like a autotype writer.



