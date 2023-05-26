# Install of a computer on debian

## Context

This is how I have configure my debian on my personnal computer.
My Computer : 

- Ryzen 9 3900x
- RTX 3080
- Aorus b550
- 64Gb Corsair Vengeance

## Nvidia

### Check the card 

```bash
lspi | grep "VGA"
## exemple output
05:00.0 VGA compatible controller: NVIDIA Corporation GA102 [GeForce RTX 3080] (rev a1)
```

[List of supported NVIDIA product](http://download.nvidia.com/XFree86/Linux-x86_64/495.46/README/supportedchips.html)


### Installation of dependencies
```bash
apt install linux-headers-$(uname -r) gcc make acpid dkms libglvnd-core-dev libglvnd0 libglvnd-dev dracut
```

### Installation of the firmware
```bash
apt install firmware-misc-nonfree
```

### Installation of the NVIDIA component
```bash
# detect the card and see with driver
apt install nvidia-detect
nvidia-detect
## exemple of output
Detected NVIDIA GPUs:
05:00.0 VGA compatible controller [0300]: NVIDIA Corporation GA102 [GeForce RTX 3080] [10de:2206] (rev a1)

Checking card:  NVIDIA Corporation GA102 [GeForce RTX 3080] (rev a1)
Your card is supported by the default drivers.
Your card is also supported by the Tesla 470 drivers series.
It is recommended to install the
    nvidia-driver
package.

###################################
# Install driver
apt install nvidia-driver
```

After the drivers installation, reboot
