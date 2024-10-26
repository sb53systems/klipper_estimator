# Klipper print time estimator

`klipper_estimator` is a tool for determining the time a print will take using
the Klipper firmware.  
  
This version has been modified to improve its integration with [G-Code Flow and Temperature Controller](https://github.com/sb53systems/G-Code-Flow-Temperature-Controller) script, forked from [Annex-Engineering/klipper_estimator](https://github.com/Annex-Engineering/klipper_estimator).  
  
The estimation is done using an implementation of Klippers kinematics, but may in some cases be slightly off due to rounding modes. If the timing is far off(e.g. more than a minute over a >12 hour print), this is considered a bug.  
  
Note that currently delta kinematic limits are _not_ implemented.  
  
### Quirks
Be aware of the following "quirks" when using `klipper_estimator` compared to Klipper itself:
  
## Building

`klipper_estimator` is written in Rust. Version 1.58 or newer is required to
compile the tool. Assuming a Rust toolchain is installed, along with git, one
can build `klipper_estimator` by running:

```
$ git clone https://github.com/sb53systems/klipper_estimator.git
$ cd klipper_estimator
$ cargo build --release
// Resulting binary will be at `target/release/klipper_estimator`(.exe on Windows)
```

## Acknowledgements

This project is in no way endorsed by the Klipper project. Please do not direct
any support requests to the Klipper project.

  * [Klipper](https://www.klipper3d.org/) by [Kevin O'Connor](https://www.patreon.com/koconnor)
  * [Moonraker](https://github.com/Arksine/moonraker) by Arksine
