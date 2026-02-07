# wt588d STANDALONE - No Programmer Required

An educational guide and toolkit for using the wt588d microcontroller without expensive or obsolete programmer hardware.

## About

I found really cheap mp3 modules off aliexpress that dont rely on those pesky abundant jieli chips poping up recently(seriously, its a jielisease). Now, wt588d and its variants use a rather weird 20khz 16bit Wav audio, but its quirky modes its what drove me to this module and also its super low idle current, the only issue is the programmer, i will go into more detail futher below


## Why This Project?

The wt588d is a useful microcontroller, but traditional programming methods require:
the ultra expensive useless(old) mini usb programmer!
This project eliminates these barriers by sharing alternative approaches discovered through searching datasheets all night

## How It Works

The wt588d stores its firmware in an **SPI Flash memory chip**. By understanding the pinout and SPI protocol:

1. The reset pin can be controlled to put the device into programming mode
2. Standard SPI interfaces can directly program the Flash
3. Any MCU with SPI capability can act as a programmer
4. No proprietary hardware required!

## Important Resources

### Documentation

- **[WT55U02 Online Application Manual](https://www.manuallib.com/download/pdf7/GUANGZHOU-WEICHUANGKJ-WT55U02-ON-LINE-APPLICATION-MANUAL.PDF)** - Essential reference showing the WT55U02-18P schematic with online download circuit and SPI Flash pinout

### Recovered Media

This project includes access to the almost lost media setup software, i hope it helps!

## Getting Started

### Hardware Options
Use ch341a/b type programmers or just any mcu spi compatible when the bin file is created on the software and put the pinout as follow

### Prerequisites

- wt588d microcontroller board with the bin file
- SPI Flash programmer interface (see Hardware Options above)
- USB cable
- Basic jumper wires for connections

### SPI Flash Pinout (from WT55U02-18P schematic)
<img width="751" height="543" alt="Captura de pantalla 2026-02-07 003448" src="https://github.com/user-attachments/assets/a8d8be14-b7f7-405d-9462-890571aa2efc" />
<img width="481" height="214" alt="Captura de pantalla 2026-02-07 004904" src="https://github.com/user-attachments/assets/83764dbe-b5f0-4e83-b552-936d1fc3edd5" />

Use this pinout for the ch341a/b or mcu equivalent and dont forget to short reset!
<img width="814" height="407" alt="image" src="https://github.com/user-attachments/assets/2c41777f-3787-4a99-a6f5-913de1d8c7f4" />

The SPI Flash memory on the wt588d uses standard SPI connections:
- **CLK** - Clock
- **DO/MISO** - Data Output (Master In, Slave Out)
- **DI/MOSI** - Data Input (Master Out, Slave In)
- **CS** - Chip Select
- **RESET** - Reset pin (tied low during programming to enable SPI access)
When on the software click compile when finished and search for a bin file, this is the file we will use on asprogrammer in case of ch341a/b and on bin flasher tools on mcus
<img width="825" height="594" alt="image" src="https://github.com/user-attachments/assets/77ce227e-5d5f-459c-a851-fea5fd4cc6df" />
<img width="672" height="168" alt="image" src="https://github.com/user-attachments/assets/0be4bbc3-7474-409a-8e3c-07ba9e80e168" />
<img width="1369" height="317" alt="image" src="https://github.com/user-attachments/assets/955f4354-3f4b-4f6c-98e4-7e99c33ecbac" />
Follow a tutorial on how to flash bin files, and thats it!

Please feel free to open an issue or submit a pull request.

## License

This is a guide, eveyone can use this!

---
