# Gentoo Deployment Script

This script facilitates the installation of Gentoo Linux on your system, either from a live CD or any live OS environment. You can download this script using links or `wget`.

## Installation Guide

1. **Run the Installation Script**:
   - Execute `setup_gentoo.sh`. This will guide you through disk provisioning or allow you to use an auto-provisioned format.

2. **Configuration Prompts**:
   - The script will ask you several configuration questions:
     - Whether to replace OpenSSL with LibreSSL (Note: LibreSSL support is being deprecated).
     - Enable LTO (Link Time Optimization) and Graphite optimizations.
     - Customize kernel options.
     - Select the platform for which you're optimizing the installation.
   - After your inputs, the script will proceed to compile and set up your system. This process might take several minutes to hours, depending on your hardware, as Gentoo requires everything to be compiled from source.

3. **Post-Installation**:
   - Once the script finishes, you'll have a fully functioning Gentoo system with a minimal kernel configuration and USE flags.  
   - Exit the chroot environment, remove the live CD, and reboot your system.

4. **Customization**:
   - After reboot, you can further customize your Gentoo system. 
   - Use `sudo deploy_rice.sh` to deploy a pre-configured GUI setup including:
     - **Window Manager**: `dwm`
     - **Terminal**: `urxvt`
     - **Status Bar**: `slstatus`
     - **File Manager**: `pcmanfm`
     - **Shells**: `zsh` and `bash`
     - **Editor**: `vim`

5. **Software Installation**:
   - Run `install_software.sh` to install additional software I use on Gentoo.

## TODOs

- **Continued Testing for Optimizations**:
  - Further test LTO & Graphite optimizations. The script currently uses the [Gentoo LTO Overlay](https://github.com/InBetweenNames/gentooLTO), which is still under development. There might be compilation issues as this overlay evolves.

- **Browser Support**:
  - Add a browser compatible with LTO and LibreSSL. Although earlier versions of Firefox worked, recent builds do not support this setup.

- **Deprecation of LibreSSL**:
  - Plan to remove LibreSSL functionality from the script as it's no longer being integrated into Gentoo and is largely abandoned by distribution developers.

## Notes

- **LTO and Graphite**: These optimizations can significantly improve performance but might also introduce compilation issues due to their experimental nature.
- **LibreSSL**: Given its deprecation, consider alternatives like OpenSSL if security or performance is a concern.

## Contributions

- Contributions and bug reports are welcome. If you encounter issues or have suggestions for improvement, please open an issue or submit a pull request.


---

Feel free to fork this repository, customize the script to better fit your needs, or share this with others interested in Gentoo Linux.
