# MT3620 Azure Sphere Based Altair 8800 Hardware

The PCB design is adapted from the open source project [Altair 8800 emulator](http://dankar.github.io/emulator/2015/04/12/altair-8800-emulator/) created by Daniel Karling. The original design files were created using KiCad, however to update the design, the PCB design file was imported into Altium, which is the format used in this version of the project. The schematic file was not imported, so please refer to Daniel Karling's original project for details.

The updates that we have made to the PCB include:

 - The original project was designed to be interfaced to an Arduino which operates at 5V, however the MT3620 operates at 3.3V. It was therefore necessary to replace some of the TTL logic with parts that are 3.3V compatible. In addition, R33 has been  replaced with a wire link.
 - All of the discrete resistors have been replaced with resistor arrays to help simplify assembly.
 - The micro-SD card holder has been replaced with a part that can more easily be hand soldered.  
 - The switches have been replaced with parts that can more easily be sourced from DigiKey
 - The overlay silkscreen has been updated to include the switch and LED functions.

## Contents

| Folder | Description |
|-------------|-------------|
| `Altium`       | Altium Designer format project and PCB files |
| `Production`       | Production files including gerber and NC drill files |

## Instructions

Please refer to the main project [documentation](https://github.com/gloveboxes/Cloud-Enabled-Altair-on-Azure-Sphere/wiki/01-introduction) for full setup and usage instructions.

## Project expectations

The project is a proof of concept. It is not official, maintained, or production-ready.

### Expected support for the code
This project is unsupported.

### How to report an issue
If you run into an issue with this project, please open a GitHub issue against this repo.

## Contributing

This project welcomes contributions and suggestions. Most contributions require you to
agree to a Contributor License Agreement (CLA) declaring that you have the right to,
and actually do, grant us the rights to use your contribution. For details, visit
https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need
to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the
instructions provided by the bot. You will only need to do this once across all repositories using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/)
or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

The license for this project is TBD.