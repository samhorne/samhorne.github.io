
# Laser Maze Hardware Documentation
Epic immersive experience featuring Python control, a custom iOS app, MQTT triggered videos and lighting, and a realtime leaderboard.

### Links
- Hardware Setup (THIS PAGE)
- Code written for this project
  - [Maze Control (Python)](https://github.com/samhorne/lasermaze2019)
  - iOS App (Swift)
  - MQTT to Core MIDI (Python)
  - [MQTT Video Trigger (Processing)](https://github.com/samhorne/mqtt-video-trigger)
  - Leaderboard (Processing)

### Parts

| Quality | Item |                                                                                               
|----------|:-----------|
| 1        | [Raspberry Pi with SD Card](raspberry.org) |                                                                                                                                                                
| 1        | [Screw Terminal Hat](https://www.amazon.com/Electronics-Salon-Terminal-Breakout-Module-Raspberry/dp/B01M27459S/ref=sr_1_2) |           
| 1        | [5V Power Supply](https://www.amazon.com/gp/product/B005T6SAJI/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)   |                    
| 3        | [8 channel Transistor Array](https://www.aliexpress.com/item/32908019845.html?spm=a2g0s.9042311.0.0.5f0b4c4dBp5TRG)     |                  
| 24       | [Laser Modules](https://www.ebay.com/itm/10pcs-650nm-6mm-5V-5mW-Red-Laser-Dot-Diode-Module-US/192413550626?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)     |                                                                          
| 1        | [32 channel Analog to Digital Converter](https://www.tindie.com/products/fercsa/32-channel-adc-wi2c-for-arduino-raspberry-pi/)      |      
| 24       | [Photoresistor](https://www.ebay.com/itm/50PCS-Photo-Light-Sensitive-Resistor-Photoresistor-Optoresistor-5mm-GL5528/401124461901?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)      |                                                   
| 1        | [Emergency Stop Button](https://www.amazon.com/gp/product/B005YX0A1M/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)   |                  
| 48       | [Barrel Jack Plugs (Male)](https://www.ebay.com/myb/PurchaseHistory#PurchaseHistoryOrdersContainer?ipp=25&Period=3&cmid=2749&_trksid=p2057872.m2749.l5117)    |                                                                                          
| 48       | [Barrel Jack Plugs (Female)](https://www.ebay.com/itm/10Pcs-DC-Power-Female-Jack-Barrel-Plug-Connector-2-1-x-5-5-mm-Terminal-US-Stock/172813450145?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)    |                                     
| 1        | [100M 20 AWG wire (4 conductor)](https://www.ebay.com/itm/4-PIN-RGB-Extension-Connector-Wire-Cable-Cord-For-3528-5050-RGB-LED-Strip-Light/162856827398?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)      |                               
| 4        | [1ft DIN Rail](https://www.amazon.com/gp/product/B07RL53HWY/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&psc=1)      |                          
| 16       | [Phoenix-Style Terminal Block (4 slot)](https://www.aliexpress.com/item/2019-NEW-10-Pcs-PT-2-5-Push-In-Din-Rail-Mounted-Terminal-Blocks-Spring-Screwless/33019362114.html?spm=a2g0s.9042311.0.0.27424c4dY4iqvx)            |                             
| 50       | [Phoenix-Style Terminal Block (2 slot)](https://www.aliexpress.com/item/2019-NEW-10-Pcs-PT-2-5-Push-In-Din-Rail-Mounted-Terminal-Blocks-Spring-Screwless/33019362114.html?spm=a2g0s.9042311.0.0.27424c4dY4iqvx)       |                                
| 2        | [DIN Mount RJ45 Breakout](https://www.amazon.com/gp/product/B07CPPJ5PL/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)           |       
| 1        | [Cat5 Cable](https://www.amazon.com/Cable-Matters-Snagless-Ethernet-Black/dp/B007NZGPAY/ref=sxin_2_ac_d_pm?ac_md=1-0-VW5kZXIgJDEw-ac_d_pm&crid=2THR8GWMSIZMG&cv_ct_cx=25+ft+cat6&keywords=25+ft+cat6&pd_rd_i=B007NZGPAY&pd_rd_r=bf59d37c-93fc-4703-b4c1-b46102c051b0&pd_rd_w=6qLCo&pd_rd_wg=dXUsd&pf_rd_p=ef07af27-e48f-451d-ab63-8b6b216a0bc3&pf_rd_r=Q5E3T73PHSD99GNQ918Y&psc=1&qid=1580249070&sprefix=25+ft+ca%2Caps%2C163&sr=1-1-22d05c05-1231-4126-b7c4-3e7a9c0027d0) |
| 1        | [Ferrules and Ferrule crimper](https://www.amazon.com/gp/product/B07212XQTV/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1)        |     
| 6        | [DIN Rail PCB Mount](https://www.aliexpress.com/item/PCB-35mm-DIN-Rail-Mounting-Adapter-Circuit-Board-Bracket-Holder-Carrier-Clips/32843068712.html?spm=a2g0s.9042311.0.0.27424c4dY4iqvx)    |                                                          
| | Scrap Wood |
|24| Plastic Food Container|
|| Diffused Plastic Wrap|

### Lasers

Each laser module is constructed with a pan/tilt bracket made from scrap wood. Barrel jack connectors make connection very quick.

Since 24 laser modules draw more current than a Raspberry Pi can handle and since they run at 5V instead of 3.3V, transistor arrays are used to offload this power from the Pi to the power supply. Each pin on the Pi triggers an individual transistor on the array with minimal current draw.
Components are mounted to a DIN rail for rugged and reliable performance.
![enter image description here](/images/lasersTB.JPG)
### Sensors
Raspberry Pi does not have an Analog to Digital Converter (ADC) built in. This means that reading analog sensors is not possible without an external ADC. This project uses a 32 channel I2C ADC to read each sensor individually. Each ACD input has a 10kΩ resistor in parallel to ground for voltage division. Pairing the ADC with RJ45 breakouts means all sensors can be mounted on an opposite wall, with a single CAT5 cable connected back to the Pi.
![enter image description here](/images/sensorsTB.JPG)
***Lesson Learned:*** I2C has distance limitations! My first attempt using a 100 ft cable failed miserably. Be sure to research the distance limitations before using a long cable, or incorporate an I2C extender.

### Button
Placing a large emergency stop button at the end of the maze allows participants to "win" the maze and deactivate the lasers. The button is connected to a Raspberry Pi pin.