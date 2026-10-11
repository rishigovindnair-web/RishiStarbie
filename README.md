# RishiStarbie
This Github Repo is a submission for Week 1 of Hackclub Halflife, where I decided to make a Starbie. A starbie is a desk pet built on a star-shaped circuit board, which has "emotions" like joy, energy, etc. You look after it through a menu where you can do things like feeding it. 

What's included

The board. The flat purple star that everything else attaches to. Thin lines of metal printed on it serve as wires, carrying electricity and data.
The brain. Tiny computer about the size of a stamp. It runs the program that controls the pet and makes things appear on the screen.
The screen. A small thin display in the middle of the star about the size of a thumbnail. This is where the pet lives.
Two buttons. Small key-like buttons, one on each side arm.
Motion sensor. Can detect orientation and shaking, like the motion sensor in your phone that tells which way it's pointing.
Temperature sensor. A small sensor that detects how hot it is, and how much humidity there is in the room.

How to play

Plug into a phone charger or a USB-C port on a computer. It doesn't have a battery, so it only powers on while it's plugged in.
The pet will begin walking side to side on the screen, trailing sparkly contrails.
Press the left button and a menu with four options appears: nap, play, feed and dance. Instead of using arrow keys, you'll use the motion sensor. Tilt the star and a small ball will begin rolling towards your desired option like a marble on a tray. Press the left button again to select it.
Each option affects the pet's happiness:
Feeding it increases happiness and fullness.
Taking a nap increases happiness and energy.
Playing and dancing increase happiness, but decrease energy.
Press the right button to access the status menu, where you can see how happy, energetic and full the pet is, and what the temperature is in the room.
Shake the star to increase the pet's happiness. If the pet was sleeping, it'll wake up.

The pet will remember its status from the last session. If you power it off and on again, it'll remember how it was feeling before you turned it off.

Everything is on the front of the star and is glued on with solder.

How a part is attached

All parts have little legs of metal on them, and the board also has holes for each leg on the part, with a ring of metal around each hole. Push the legs of the part through the holes from the front so that the part rests on the front of the star (not on its side), then flip it over.

On the back, touch the soldering iron to where the leg of the part and the ring of metal on the board meet, and add a little solder. Solder is a metal wire that melts easily, and when you melt some of it, it will pool around the leg and metal ring, and then harden in a couple seconds. This does two things:

It physically holds the part in place, and

it makes an electrical connection, so that electricity can flow from the part to the lines on the board.

After soldering a leg, you can cut off the excess part of the leg on the back of the star.

The three mini boards

The brain, the screen, and the motion sensor each come as their own mini board, so each needs one extra step. They probably come with a little strip of metal pins on the side, which you have to solder onto the mini board first, making it have legs to solder in the star. Then solder those legs into the star like normal.

Where everything goes

On top: temperature sensor and the little resistor next to it, in the middle: the screen, on the left and right points: a button each, on the bottom left: the motion sensor, on the bottom right: the brain, whose USB-C port juts out over the bottom edge.

Order to do it in

The parts that are on the very bottom of the star (so that the star can lay flat on a desk) should be soldered on first: resistor (a little part with two legs of wire), temperature sensor, brain, motion sensor, and screen. Then the buttons, and finally the keycaps, which just snap onto the buttons and don't need to be soldered.

The motion sensor has pins that stick out a long way underneath, so trim those to a reasonable length, or the star won't be able to lay flat on a desk.

Images: 
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

| Part | Store | Link | Need | Buy | Price |
| :--- | :--- | :--- | :--- | :--- | :--- |
| XIAO ESP32-C3 | Seeed Studio | XIAO ESP32C3 | 1 | 1 | $4.99 |
| 0.96" OLED, GND-VCC-SCL-SDA | 52Pi | 52Pi 0.96" OLED | 1 | 1 set | $5.09 |
| MPU6050 (GY-521), comes with its 8 pins | ProtoSupplies | MPU-6050 GY-521 | 1 | 1 | $3.95 |
| 10k resistor | ProtoSupplies | 10k resistor, 25-pack | 1 | 1 pack of 25 | $0.59 |
| Header pins, 1×40 strips | ProtoSupplies | Male header 1x40, 5-pack | 18 (14 for the XIAO + 4 for the OLED) | 1 pack of 5 strips | $0.95 |
| DHT11, bare 4-pin | LCSC | Aosong DHT11 (C117051) | 1 | 1 | $1.46 |
| MX-compatible switches | Adafruit | Kailh Clicky White, 10-pack | 2 | 1 pack of 10 | $6.95 |
| Keycaps | Adafruit | Dark Gray DSA keycaps, 10-pack | 2 | 1 pack of 10 | $5.95 |
| PCB | JLCPCB | jlcpcb.com (upload RishiStarbie_gerbers.zip) | 1 | 5 (minimum order) | $2.00 + ~$1.20 tariff |
| **Parts and board subtotal** | | | | | **$33.13** |
