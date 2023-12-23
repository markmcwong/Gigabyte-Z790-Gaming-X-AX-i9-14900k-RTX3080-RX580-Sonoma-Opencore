Notes:
- AppleKeyStore error happens when you are in verbose mode, just disable
- Add flag -global ICH9-LPC.acpi-pci-hotplug-with-bridge-support=off
- Need to add USB mouse to make evdev mouse work - or else mouse won't move
- Need to run `sudo virsh net-autostart default` to start automatically
- Need to enable HDMI audio by changing HDMI audio's PCI (05:00.1) to same bus as gpu then have `function="0x1"` (https://www.reddit.com/r/VFIO/comments/x46bf5/osxkvm_trouble_passing_onboard_audio/)
- No way to have Broadcom card passed working for now (Crash VM when try to connect to wifi)

- Need to modify GRUB to block out device IDs for passthrough
- qemu runs as user/group `evdev` under
- kvm and libvirt added to `etc/security/limits.conf`

Files Paths:
- /etc/modprobe.d/blacklist.conf                              
- /etc/modprobe.d/vfio.conf
- /etc/libvirt/qemu.conf
- /etc/security/limits.conf
