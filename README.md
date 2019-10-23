# qemu_sk_deb_install

                                            QEMU DEB INSTALL AND RUN 

                                            =========================


This is a installation debian package for Savira Kotigalu (Thousand Monkeys) qemu HID usb educational device. When installed this deb package, QEMU devices will have a new USB hid device called 'usb-sk-kbd'. It is a HID device can be used as a auto typewriter when attached to a virtual machine. Whenever, it is attached to a virtual machine while booting up, it creates a FIFO write end at /tmp/kotigalu directory, with corresponding process ID of the qemu. Users, can just write text into FIFO and mount the cursor on a editor, the usb-sk-kbd starts pumping in characters like a auto typewriter.

INSTALL

=======

Run install script as below, 

    $sh install.sh

Ater installation, to list the usb-sk-kbd device run,

$kvm-spice -device ?

Search for usb-sk-kbd device under 'Input devices'         


RUNNING QEMU FROM COMMANDLINE

============================

Ex:

Booting up dsl-4.4.10.iso linux iso

kvm-spice -m 1024 -enable-kvm -drive if=virtio,file=test.qcow2,cache=none  -usb -device usb-sk-kbd -cdrom dsl-4.4.10.iso

Ex:

Booting up a windows img

kvm-spice -m 1024 -enable-kvm -drive if=virtio,file=test.qcow2,cache=none  -usb -device usb-sk-kbd -boot d box.img

Options:

-------

-driver                       Create a qcow2 image and pass absolute path of the image

                              Ex: qemu-img create -f qcow2 test.qcow2 16G

-usb -device  usb-kbd         Is the syntax for passing the custom keyboard.

-cdrom                        Use this flag if you are using .iso to boot up

-boot d                       Use this flag if you are using a .img to boot up

-- End








