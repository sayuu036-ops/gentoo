```
# --- Firecracker guest kernel: the load-bearing symbols (fragment) ---
# virtio transport over MMIO (Firecracker does NOT use PCI)
CONFIG_VIRTIO=y
CONFIG_VIRTIO_MMIO=y

# the microVM's only real "hardware"
CONFIG_VIRTIO_BLK=y          # rootfs disk
CONFIG_VIRTIO_NET=y          # network via host TAP
CONFIG_VIRTIO_VSOCKETS=y     # guest<->host control channel
CONFIG_HW_RANDOM_VIRTIO=y    # entropy from the host

# serial console so you can see boot + panics on ttyS0
CONFIG_SERIAL_8250=y
CONFIG_SERIAL_8250_CONSOLE=y
```

general setup  
	configure standard kernel features  
		enable support for printk  
device driver  
	character devices  
		enable tty  
		virtio console  
		hardware random number generator core support  
			virtio random number generator support  
	network device support  
		virtio network driver  
	block devices  
		virtio block driver  
64-bit support  
enable the block layer  
networking support  
	networking options  
		virtual socket protocol
