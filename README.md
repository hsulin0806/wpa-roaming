# wpa-roaming

This project contains a patch file that can be applied to the source code of [wpa_supplicant](http://w1.fi/wpa_supplicant/) on Ubuntu machines to make its roaming behaviour less sensitive. A more thorough discussion of this patch is available in [my German-language Linux blog](https://linux.timschroeder.net/2017/08/14/raetselhaftes-wlan-roaming.html).

## Usage

To include this patch into wpa_supplicant, follow the below instructions. 

### Prepare

Download the wpa_supplicant source code via `sudo apt-get source wpasupplicant`, then apply the patch. 

### Compile

First, satisfy the build dependencies by running `sudo apt-get build-dep wpasupplicant` . Then, copy the configuration file that is in `wpa_2.4-0ubuntu9.debian.tar.xz/debian/config/wpasupplicant/linux` to the root directory of the source code, renaming it to `.config`. Then, compile wpa_supplicant using `make`. 

### Deploy

Move the modified wpa_supplicant executable into the right location on your machine (which should be `/sbin`). Before you can do that, you must stop the network-manager via `sudo service network-manager stop` and kill wpa_supplicant via `sudo pkill -9 wpa_supplicant$`. Afterwards, start the network-manager again via `sudo service network-manager start`. 