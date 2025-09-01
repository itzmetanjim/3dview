## Hardware needed (parts list)
Since no encoder DC motors exist in the inventory, I will use stepper motors.
Here are the parts:
- ### 2.8" Touchscreen
2.8" TFT LCD(tpm408-2.8)

BOM Name: touchscreen

Quantity needed: 1
reference link https://www.amazon.com/HiLetgo-240X320-Resolution-Display-ILI9341/dp/B073R7BH1B

This is the display. It will be spinning.

### OR 1.8" Screen
1.8" 160x128 ST7735 TFT Display

BOM Name: 1.8-screen

Quantity: 9
reference link https://www.digikey.com/en/products/detail/adafruit-industries-llc/358/5801368?gclsrc=aw.ds&gad_source=1&gad_campaignid=20228387720&gbraid=0AAAAADrbLlj6J1-CXjMvB2poJDP6vXZk8&gclid=Cj0KCQjwtMHEBhC-ARIsABua5iSUqiseLrZ0jIoWnQQAKtPOi3Fta5P42dNPiDKyF84q20x1jw7Lat0aAqg6EALw_wcB

but there is no apparent reason to take a smaller screen, we will see

- ### Stepper Motor
Nema 17

BOM Name: Nema-17-stepper

Quantity: 10
reference link https://www.amazon.com/YEJMKJ-Stepper-17HS4401-Connector-1-57inch/dp/B0CDRMHM82/ref=sr_1_2_sspa?crid=181XC8N7UHZ0P&dib=eyJ2IjoiMSJ9.hN-9QQUUabt-Xybqh_2heY2GPNfYHPQMKSJH70tSBpLnCSZy6_e4_Umlwx4n7WEnj8SUjuFicclvOjZjQyMVj0s8lHhFLwfOQ1F_F1ZnAAwouPtBesnkdpUfBlHTfemFjxwxaxP_4JSa_-u6-0lT6Tg5UskI8vrpXBoMRtqi_D4LXQ8jktkAzk2mf85fvbEElxlsyWmhcZW4KZcs0_zLv4JkWpkJ5WIri-U6u1KZ1AQ.1JSO5KS-1o3BAukDWPR5JbUyQ5H3m3-ufwoAov2IL3E&dib_tag=se&keywords=nema+17+stepper+motor&qid=1754065240&sprefix=nema+17+steppe%2Caps%2C243&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1

### Raspberry Pi Pico W
Has wifi!

BOM Name: RP-Pico-W

Quantity: 1
reference link https://www.amazon.com/Pico-Raspberry-Pre-Soldered-Dual-core-Processor/dp/B0BK9W4H2Q/ref=sr_1_1?crid=1T25Y3V0OADAK&dib=eyJ2IjoiMSJ9.s_twZ2XW26kpBo4nU7Zh7Px7g4DEnPvai1Qk2u8urjOcOm3IIPrxYt_NfdE62sxyBUazkFLpcypqA5nfgoFGD6lKXqVOxq62vd4AaGj5iD3hzA9_EYOQOL2NMd2X3TqPi-hIo3veQj1iOuboa2W8zmBKtainTgaTWGeVcCbvFJHPqJvLtkmo6VSjrof9PJeecopnWAccAwm0TiOClayNgb3vTAu9WgrvXu45gRt0MVU.pz4nHZml1q9zIvhs753NqAHJJfPW6kC2BmIgrsoZhOA&dib_tag=se&keywords=Raspberry+Pi+Pico+W&qid=1754065716&sprefix=raspberry+pi+pico+w%2Caps%2C139&sr=8-1

reason i choose RPi Pico: it has USB! ALSO i will not program in c++ unless i have to, 
This will not be spinning

### Stepper Motor Driver
A4988 Stepstick Stepper Motor Driver Module

BOM Name: stepper-driver

Quantity: 1
reference link https://www.amazon.com/HiLetgo-Stepstick-Stepper-Printer-Compatible/dp/B07BND65C8/ref=sr_1_1_sspa?crid=1HOPWZTL1PXVN&dib=eyJ2IjoiMSJ9.iVQPfiXcfapsptSjTWffZJlKusTsCb7EARpgtMTTOGfzc2_TkjwMeP22ZnSShqDhv9XOdZJhb49PfOdkFoSc2uBv9-FcbTLkvf9Gdcz_0SOfUnUbBhTdcSP7b6mQEGjw7KyUj8z4InY3HgVQKe5Pz5MhV4FeB2EDn3vCyMKVQSPn2DdIdcDscVbNZYpyBlUYt2KgUNLxePZbP-6M_PEaGY09NLan8OjSM0EpwViublA.9xODxjaBiCLgidNpWDU0LqQXqY46c120kG6ssyQDPGw&dib_tag=se&keywords=stepper+motor+driver&qid=1754065274&sprefix=stepper+motor+drive%2Caps%2C117&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1

i need a driver to drive the motor, which will not be spinning (attached to base)


### i removed this i dont think i need it serial is good enough
```
### (what they call a) Large Screen
GME12864-11, SSD1306

BOM Name: large-screen

Quantity: 1
reference link https://www.amazon.com/Hosyond-Display-Self-Luminous-Compatible-Raspberry/dp/B09T6SJBV5/ref=sr_1_1_sspa?crid=2ARFT212EUKPS&keywords=GME12864-11%2C%2BSSD1306&qid=1754063592&sprefix=gme12864-11%2C%2Bssd1306%2B%2Caps%2C182&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1

they call it "large screen" this is literally a tiny 0.96inch (diagonal) screen. I will use it as an informational screen not attached to the 3d spinning screen, this will be helpful.
```
## alright these were the parts from inventory, but i also need more parts
## here is the list

### Slip Ring
[note to reviewers: i took a long time to find a cheap slip ring, like 30 mins]
link
https://www.aliexpress.com/item/32984731269.html?spm=a2g0o.productlist.main.2.62e54Nfl4Nfljq&algo_pvid=ca8dd6c8-ab27-444e-906d-e37d61173a68&algo_exp_id=ca8dd6c8-ab27-444e-906d-e37d61173a68-1&pdp_ext_f=%7B%22order%22%3A%2236%22%2C%22eval%22%3A%221%22%7D&pdp_npi=6%40dis%21USD%217.49%216.74%21%21%217.49%216.74%21%40213ba0c517566563835206704e332e%2166742831070%21sea%21BD%210%21ABX%211%210%21n_tag%3A-29910%3Bd%3Abf8ba9eb%3Bm03_new_user%3A-29895&curPageLogUid=bXeMngxs3mED&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A32984731269%7C_p_origin_prod%3A

price: us$8.99 (ships to bangladesh)
this is a cheap 8 wire slip ring with 2A.
i need 8 wires since i dont use touch, and SDO (reading from display) would be useless here.
VCC
GND
SPI
CS 
RESET
D/C 
SDI 
SCK
LED
are the wires i need.
since i need to use atleast the 20$ grant I need to work for more than 3h. But making this plan took 1h, so no problem i guess.

### 3D print

through #printing-legion
price: ??? whatever it takes to ship

### OR: a bare pcb
price: free