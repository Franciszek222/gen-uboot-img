# U-boot for Samsung J5 2016

All devices supported by lk2nd and msm8916-mainline should be supported. You might need dts file for your device.

## Download required submodules
You will need to collect a selection of projects to build the bootchain.

- git clone https://github.com/msm8916-mainline/lk2nd.git
- #msm8916 Linux kernel; git clone https://github.com/msm8916-mainline/linux.git
- git clone https://github.com/Franciszek222/u-boot.git
- git clone https://github.com/msm8916-mainline/qhypstub.git

Build system expects those repositories to exist in the parent dir of the project.
See Makefile on how to override the path.

After collecting and checking out desired branches on these repositories, run:

```
make -j$(nproc)
```

This will builds all the projects and place artifacts in `build/`.

## Usage

U-boot should launch `/boot/efi/bootaa64.efi` from the storage if it finds it.
This should be sufficient to boot most generic EFI capable system images.
