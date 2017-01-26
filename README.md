## Pine Boot Tools

This is simple repository that has scripts and binaries to
aid with booting of Pine A64 and Pinebook.

This repository is primarily meant to access Pine as USB mass
storage when using USB A-to-A cable.

This requires for your device to be run in FEL mode.

### How to run device in FEL mode?

For Pine A64 remove SD card, power on device and insert SD card.

For Pinebook, longpress power button till the power led is ON,
then do a few short presses, each one of about 0.4-0.5s.
After a while device should start in FEL mode.

### How to start UMS (USB mass storage mode)?

```bash
$ git clone https://github.com/ayufan-pine64/boot-tools.git
$ cd boot-tools
$ make pinebook_ums
or
$ make pine64_ums
```

### How to recompile everything?

```bash
$ git clone https://github.com/ayufan-pine64/boot-tools.git
$ cd boot-tools
$ rm -rf build
$ make
```

### What it contains?

1. The modified u-boot to present itself as a USB mass storage device,
2. The special work mode (0x55) implemented in u-boot that performs storage scan,
   and runs special USB mass storage command on boot,
3. The SPL code that initializes DRAM and allows to run custom made u-boot,
4. Compiled binary blobs,
5. The original `boot0's` in `blobs/` and DTS for Pine A64 and Pinebook.

### Convert existing images to Pinebook

Here you can also find a compiled boot0 and u-boot (with included dtb)
which is suitable to be put onto device.

The Pinebook requires you to put a compiled dtb onto first partition
at `pine64/sun50i-a64-pine64-pinebook.dtb`,
and copying the `boot/` content to the disk.

### Author

Kamil Trzciński, 2017

### License

MIT
