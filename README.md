# RishiStarbie

My Starbie for Week 1 of Hack Club Half-Life. A Starbie is a desk pet built on a star-shaped circuit board. It has "emotions" like joy and energy, and you look after it through a menu where you can do things like feed it.

## Repo layout

```
RishiStarbie/
├── firmware/RishiStarbie/            Arduino sketch for the XIAO ESP32-C3
├── pcb/                              KiCad project (open this)
│   ├── RishiStarbie.kicad_pro
│   ├── RishiStarbie.kicad_sch        schematic
│   ├── RishiStarbie.kicad_pcb        board layout
│   ├── fp-lib-table / sym-lib-table  point KiCad at libs/
│   └── libs/
│       ├── Imported Parts.pretty/    footprints: XIAO ESP32-C3, OLED, MPU6050
│       ├── Seeed_Studio_XIAO_Series.kicad_sym
│       └── 3D Models/                see the README in there
└── production/
    ├── RishiStarbie_gerbers.zip      upload this to JLCPCB
    └── BOM.csv
```

## Editing in KiCad

1. Install KiCad 7 or newer (the files are saved in KiCad 7 format, so 8 and 9 open them too).
2. Clone or download this repo. Keep the folder structure as it is.
3. Open `pcb/RishiStarbie.kicad_pro`. The schematic and PCB editors open from there.

The custom footprints and the XIAO symbol live in `pcb/libs/`, and the project's library tables point at them with `${KIPRJMOD}`, so they load on any computer without extra setup. Everything else (switches, DHT11, resistor, connectors) comes from KiCad's built-in libraries.

If you change the board, re-export gerbers (File → Fabrication Outputs → Gerbers + Drill Files), zip them, and replace `production/RishiStarbie_gerbers.zip`.

## Firmware

The code is in [`firmware/RishiStarbie/RishiStarbie.ino`](firmware/RishiStarbie/RishiStarbie.ino).

1. Install the [Arduino IDE](https://www.arduino.cc/en/software).
2. Add ESP32 support: File → Preferences → "Additional boards manager URLs", paste `https://espressif.github.io/arduino-esp32/package_esp32_index.json`, then install **esp32 by Espressif** from Tools → Board → Boards Manager.
3. Install these libraries from Sketch → Include Library → Manage Libraries (click "Install All" when it asks about dependencies): **Adafruit GFX Library**, **Adafruit SSD1306**, **Adafruit MPU6050**, **DHT sensor library**.
4. Open the `.ino`, pick Tools → Board → esp32 → **XIAO_ESP32C3**, plug in the Starbie, choose its port, and click Upload.

Pin numbers, starting stats, menu actions and the pet sprite are all in the `BEGINNER SETTINGS` section at the top of the file. The pins there match the PCB: SDA on D4, SCL on D5, DHT11 on D1, left button on D2, right button on D3.

## What's on the board

- **The board.** The flat purple star that everything else attaches to. Thin lines of metal printed on it serve as wires, carrying electricity and data.
- **The brain.** A tiny computer (Seeed XIAO ESP32-C3) about the size of a stamp. It runs the program that controls the pet and draws on the screen.
- **The screen.** A small 0.96" OLED in the middle of the star, about the size of a thumbnail. This is where the pet lives.
- **Two buttons.** Small key-like buttons, one on each side arm.
- **Motion sensor.** An MPU6050 that detects orientation and shaking, like the sensor in your phone that tells which way it's pointing.
- **Temperature sensor.** A DHT11 that reads the temperature and humidity in the room.

## How to play

Plug it into a phone charger or a USB-C port on a computer. It doesn't have a battery, so it only runs while plugged in.

The pet walks side to side on the screen, trailing sparkly contrails.

Press the left button and a menu with four options appears: nap, play, feed and dance. Instead of arrow keys you use the motion sensor. Tilt the star and a small ball rolls toward the option you want, like a marble on a tray. Press the left button again to select it.

Each option affects the pet:

- Feeding increases happiness and fullness.
- Napping increases happiness and energy.
- Playing and dancing increase happiness but use up energy.

Press the right button for the status menu, which shows how happy, energetic and full the pet is, plus the room temperature.

Shake the star to make the pet happier. If it was sleeping, it wakes up.

The pet remembers its status between sessions. Unplug it and plug it back in and it'll still feel the way it did.

## Building it

Everything goes on the front of the star and is held on with solder.

### How a part is attached

All parts have little metal legs, and the board has a hole for each leg with a ring of metal around it. Push the legs through the holes from the front so the part sits flat on the front of the star (not on its side), then flip the board over.

On the back, touch the soldering iron to where the leg meets the metal ring and add a little solder. Solder is a metal wire that melts easily. It pools around the leg and ring and hardens in a couple of seconds. That does two things:

1. It physically holds the part in place.
2. It makes an electrical connection, so electricity can flow from the part to the lines on the board.

After soldering a leg, snip off the extra length sticking out the back.

### The three mini boards

The brain, the screen and the motion sensor each come on their own mini board, so they need one extra step. They usually come with a strip of metal header pins. Solder the pins onto the mini board first, which gives it legs, then solder those legs into the star like normal.

### Where everything goes

- Top: temperature sensor, with the little resistor next to it
- Middle: the screen
- Left and right points: one button each
- Bottom left: the motion sensor
- Bottom right: the brain, with its USB-C port sticking out over the bottom edge

### Order to do it in

Solder the parts that sit lowest on the star first, so it can still lie flat on a desk while you work: resistor (the little part with two wire legs), temperature sensor, brain, motion sensor, and screen. Then the buttons. The keycaps go on last and just snap onto the buttons, no solder needed.

The motion sensor's pins stick out a long way underneath. Trim them short or the star won't lie flat.

## Parts list

| Part | Store | Link | Need | Buy | Price |
| :--- | :--- | :--- | :--- | :--- | :--- |
| XIAO ESP32-C3 | Seeed Studio | [XIAO ESP32C3](https://www.seeedstudio.com/Seeed-XIAO-ESP32C3-p-5431.html) | 1 | 1 | $4.99 |
| Header pins, 7-pin XIAO headers | Seeed Studio | [7-pin male header, 5 pcs](https://www.seeedstudio.com/XIAO-Series-7-Pin-Male-Header-5-pcs-p-5460.html) | 18 (14 for the XIAO + 4 for the OLED) | 1 pack of 5 | $0.20 |
| 0.96" OLED, GND-VCC-SCL-SDA | 52Pi | [52Pi 0.96" OLED](https://52pi.com/products/52pi-oled-display-module-i2c-iic-128x64-pixel-0-96-inch-display-module-yellow-blue-two-color-display-compatible-with-raspberry-pi-arduino-51-series-mcu-stm32-r3-and-mega) | 1 | 1 set | $5.09 |
| MPU6050 (GY-521), comes with its 8 pins | Amazon | [GY-521 MPU-6050 module](https://www.amazon.com/dp/B0CP78F4TQ) | 1 | 1 | $4.95 |
| DHT11, bare 4-pin | Amazon | [4-pin DHT11 sensor](https://www.amazon.com/dp/B0HFRZSYCQ) | 1 | 1 | $6.46 |
| 10k resistor | Adafruit | [10k resistor, 25-pack](https://www.adafruit.com/product/2784) | 1 | 1 pack of 25 | $0.75 |
| MX-compatible switches | Adafruit | [Kailh Clicky Blue, single](https://www.adafruit.com/product/5123) | 2 | 2 | $1.90 |
| Keycaps | Adafruit | [Translucent keycaps for MX, 10-pack](https://www.adafruit.com/product/4956) | 2 | 1 pack of 10 | $4.95 |
| PCB | JLCPCB | [JLCPCB instant quote](https://cart.jlcpcb.com/quote) (upload `production/RishiStarbie_gerbers.zip`) | 1 | 5 (minimum order) | $0.01 |
| **Parts and board subtotal** | | | | | **$29.30** |
| Tax & shipping (Seeed $6.30, 52Pi $6.00, Amazon $4.41, Adafruit $7.46) | | | | | $24.17 |
| **Total** | | | | | **$53.47** |

The same list with reference designators and footprints is in [`production/BOM.csv`](production/BOM.csv).

## Build journal images

<details>
<summary>Screenshots from the schematic, layout and DRC steps (click to expand)</summary>

<img width="1441" height="1235" alt="s3-silk-back" src="https://github.com/user-attachments/assets/c36d1dec-c384-4269-9a88-e530127dec6d" />
<img width="1441" height="1274" alt="s3-silk" src="https://github.com/user-attachments/assets/5658be0e-ec0b-49b4-a1b3-a704ba7c0cfe" />
<img width="939" height="1055" alt="s3-jlcpcb" src="https://github.com/user-attachments/assets/6ccf4df6-39fb-475b-9ac8-e5d13acaddc2" />
<img width="1415" height="1203" alt="s3-front" src="https://github.com/user-attachments/assets/7c6bff7c-7b3e-4c47-8850-b1e30ae6b05f" />
<img width="707" height="566" alt="s3-drc" src="https://github.com/user-attachments/assets/08c5ce1c-99d5-4faa-912a-501539022114" />
<img width="1447" height="1177" alt="s3-back" src="https://github.com/user-attachments/assets/5c3bdb99-5aee-4811-a032-78a537f0e432" />
<img width="939" height="1055" alt="s3-07" src="https://github.com/user-attachments/assets/26b9d45f-8776-4944-aab9-bc46942b8ff4" />
<img width="1441" height="1235" alt="s3-06" src="https://github.com/user-attachments/assets/10059bbc-dc0e-4e7c-ae09-e88ba771107f" />
<img width="1441" height="1274" alt="s3-05" src="https://github.com/user-attachments/assets/82598cf7-4a62-4ce1-b154-ca208f760d69" />
<img width="707" height="566" alt="s3-04" src="https://github.com/user-attachments/assets/61cd7cd1-7c94-473a-8635-9828cafdd01f" />
<img width="752" height="514" alt="s3-03" src="https://github.com/user-attachments/assets/17f67c9f-f035-4d4f-b0ca-d7d6f15114b1" />
<img width="1447" height="1177" alt="s3-02" src="https://github.com/user-attachments/assets/d07a90ca-559a-486f-b901-83d9acf7497d" />
<img width="1415" height="1203" alt="s3-01" src="https://github.com/user-attachments/assets/e738bd8a-5360-4882-8e0b-43e70d3448c0" />
<img width="862" height="527" alt="s2-placement" src="https://github.com/user-attachments/assets/87129d81-d321-4900-a659-1ce958983b39" />
<img width="862" height="527" alt="s2-05" src="https://github.com/user-attachments/assets/751de3a9-f0ee-46ac-bc3d-5991649e53df" />
<img width="2149" height="1267" alt="s1-schematic" src="https://github.com/user-attachments/assets/ab3bfffc-67d9-4c2d-b10e-c171efa0166b" />
<img width="1210" height="423" alt="s1-libraries" src="https://github.com/user-attachments/assets/ce85dca7-55a8-4de6-8d66-2b2ac8169d76" />
<img width="926" height="347" alt="s1-07" src="https://github.com/user-attachments/assets/598f5745-14d3-41b5-82c5-ebf85b9e3185" />
<img width="656" height="521" alt="s1-06" src="https://github.com/user-attachments/assets/76089d43-8ed5-4108-8e3d-18ef554500a8" />
<img width="2149" height="1267" alt="s1-05" src="https://github.com/user-attachments/assets/6c22bc39-a0b8-4b75-bde6-037b2031bfd3" />
<img width="1325" height="1196" alt="s1-04" src="https://github.com/user-attachments/assets/83d7373b-e0a4-4912-bebc-26d5802eebff" />
<img width="1210" height="423" alt="s1-03" src="https://github.com/user-attachments/assets/40f305e7-66b6-493c-add4-991aed27b95b" />
<img width="1156" height="195" alt="s1-02" src="https://github.com/user-attachments/assets/7bfa3f0e-2966-45ef-a18f-cfcf2183017f" />
<img width="219" height="200" alt="s1-01" src="https://github.com/user-attachments/assets/92d739f2-f518-4b7f-864c-61a46f197191" />
<img width="508" height="257" alt="Journal2_6" src="https://github.com/user-attachments/assets/b251de90-9fec-4f9f-8767-d109f3e8597b" />
<img width="1499" height="675" alt="Journal2_5" src="https://github.com/user-attachments/assets/354a5aa6-7165-418e-a039-ef9159c3da9e" />
<img width="1666" height="1184" alt="Journal2_4" src="https://github.com/user-attachments/assets/8e53c5eb-c7b5-45d9-87ba-60080e136ed9" />
<img width="1029" height="649" alt="Journal2_3" src="https://github.com/user-attachments/assets/49b4122a-c23d-4c90-9a6d-2eeadb6cf300" />
<img width="1003" height="604" alt="Journal2_2" src="https://github.com/user-attachments/assets/ab858e63-dee9-4ba1-9616-84348ae8b5f3" />
<img width="1441" height="1229" alt="Journal2_1" src="https://github.com/user-attachments/assets/961d88a8-0dd2-45ef-a2e0-493b3f8f5cad" />

</details>
