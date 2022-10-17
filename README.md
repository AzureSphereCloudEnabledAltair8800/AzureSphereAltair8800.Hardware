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

Please refer to the main project [documentation](https://github.com/AzureSphereCloudEnabledAltair8800/AzureSphereAltair8800/wiki) for full setup and usage instructions.

## Front panel wiring

### Seeed Studio Azure Sphere development Kit


Altair Front Panel Pin No. | Function | MT3620 Pin | MT3620 Pin Function | Description
--------|----------|------------|---------------------|------------
1 | Switches Load | H4/P14 | GPIO40 | Active low load switch data into shift registers
2 | Switches Chip Select | H4/P12 | GPIO37 | Switch 'chip select' - active low enable for shift registers that read switch states
4 | MISO | H4/P5 | MISO1 | SPI MISO
5 | MOSI | H4/P11 | MOSI1 | SPI MOSI
6 | MR | H4/P10 | GPIO39 | Active low master rest of shift registers that control the LEDs
7 | CLK | H4/P7 | SCLK1 | Clock input
8 | LED Store | H4/P8 | GPIO36 | Clocks data from the shift registers into the storage registers that control the LEDs
9 | LED Output Enable | H4/P6 | GPIO38 | Active low output enable for the shift registers that control the LEDs
10 | VCC | H3/P3 | 3.3 V | +3.3 V
11 | GND | H3/P2 | GND | Ground

### Avnet Azure Sphere Starter Kit Rev 1 & 2

Altair Front Panel Pin No. | Function | Click Pin | MT3620 Pin Function | Description
--------|----------|------------|---------------------|------------
1 | Switches load | CLICK 1: AN | GPIO42 | Active low load switch data into shift registers
2 | Switches Chip Select | CLICK 1: RST | GPIO16 | Switch 'chip select' - active low enable for shift registers that read switch states
4 | MISO | CLICK 1: MISO | MISO1 | SPI MISO
5 | MOSI | CLICK 1: MOSI | MOSI1 | SPI MOSI
6 | MR | CLICK 1: PWM | GPIO0 | Active low master rest of shift registers that control the LEDs
7 | CLK | CLICK 1: SCK | SCLK1 | Clock input
8 | LED Store | CLICK 1: INT | GPIO2 | Clocks data from the shift registers into the storage registers that control the LEDs
9 | LED Output Enable | CLICK 1: RX | GPIO28 | Active low output enable for the shift registers that control the LEDs
10 | VCC | CLICK 1: 3.3 | 3.3 V | +3.3 V
11 | GND | CLICK 1: GND | GND | Ground

### Raspberry Pi Header

Altair Front Panel Pin No. | Function | Raspberry Pi Pin | Pin Function | Description
--------|----------|------------|---------------------|------------
1 | Switches load | 29 | GP 05 | Active low load switch data into shift registers
2 | Switches Chip Select | 27 | GP 00 | Switch 'chip select' - active low enable for shift registers that read switch states
4 | MISO | 21 | MISO | SPI MISO
5 | MOSI | 19 | MOSI | SPI MOSI
6 | MR | 15 | GP 22 | Active low master rest of shift registers that control the LEDs
7 | CLK | 23 | CLK | Clock input
8 | LED Store | 13 | GP 27 | Clocks data from the shift registers into the storage registers that control the LEDs
9 | LED Output Enable | 11 | GP 17 | Active low output enable for the shift registers that control the LEDs
10 | VCC | 17 | 3.3 V | +3.3 V
11 | GND | 9 | GND | Ground

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
