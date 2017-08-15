# wpa-roaming

This project contains a patch file that can be applied to the source code of [wpa_supplicant](http://w1.fi/wpa_supplicant/) on Ubuntu machines to make its roaming behaviour less sensitive. 

## How to Use It

To include this patch into wpa_supplicant, download the wpa_supplicant source code via `sudo apt-get source wpasupplicant`, then apply the patch. Compile wpa_supplicant using `make` (after resolving all build dependencies and preparing a `.config` file) and move the modified wpa_supplicant executable into the right location on your machine (which should be `/sbin`). I have included a modified wpa_supplicant executable (based upon wpa_2.4-0ubuntu9) in this repository.

## Further Information

A more thorough discussion of this patch is available in [my German-language Linux blog](https://linux.timschroeder.net/2017/08/14/raetselhaftes-wlan-roaming.html).