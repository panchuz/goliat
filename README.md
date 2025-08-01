# goliat

hardware conflicts
drivers; IT8721F, wifi, other?

overclocking
stress tests


partition gat beforehand?
.MBR
.ext4 for boot?
./home partition? or subvolume?
subvolumens?

---------- Debian Trixie ----------
installation:
.minimal? typical?
.net installation?
.night builds?
.root account?
.office suite?
.xfce add-ons?

### ARGENTINA

REPOSITORIES!!!!
```
sudo tee /etc/apt/sources.list << 'EOF'  
deb http://deb.debian.org/debian trixie main contrib non-free  
deb http://deb.debian.org/debian-security trixie-security main contrib non-free  
deb http://deb.debian.org/debian trixie-updates main contrib non-free  
EOF

sudo apt update  
sudo apt install build-essential linux-headers-$(uname -r) dkms  
```


## IT8721F Super I/O chip
fork https://github.com/frankcrawford/it87 to panchuz ???
install linux headers
install git


```
sudo apt install build-essential linux-headers-$(uname -r) git
git clone https://github.com/panchuz/it87
cd it87
sudo make dkms  # Auto-rebuilds on kernel updates :cite[1]
```
Note: forked from https://github.com/frankcrawford/it87

Kernel parameters
nohpet,
mitigations=off,
idle=poll???? FX-series C6 state bugs
radeon.dpm=1	Enables dynamic GPU power management	Reduces GPU heat/noise (requires firmware)
