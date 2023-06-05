## Adafruit NeoDriver - I2C to NeoPixel Driver Board - Stemma QT PCB

<a href="http://www.adafruit.com/products/5766"><img src="assets/5766-05.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit NeoDriver - I2C to NeoPixel Driver Board - Stemma QT. 

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/5766

### Description

NeoPixel LEDs (a.k.a WS2812 / SK6812 family) are a super-easy way to add addressable RGB lighting with only one GPIO. They're ubiquitous on microcontrollers, but some chips or single board computers (SBCs) don't have neopixel support due to the precision timing required to send data.

We often get folks asking how to get NeoPixels working on some OrangeBananaOnionRockchipAllWinner Pi type board, given we have our Blinka library that provides support for CircuitPython libraries including the NeoPixel library. But if theres no neopixel_write implementation written for that platform, it just wont work. And writing the neopixel-writer function is non-trivial on many chips: you really need fast GPIO and nanosecond-perfect timing.

A quick solution is this seesaw-based NeoDriver board here: send it the NeoPixel data you want to write over I2C and it will blit out the perfect pixel timing on the other side. We're using an ATtiny1616 so we have enough RAM to buffer a 512-pixel long strand. now, to be fair - its not super fast because we have to write each pixel over I2C, but with a 800KHz or 1MHz I2C clock and as long as you're not writing the whole strip at once, its not so bad!

We add a 5V charge-pump so even on 3V boards, you'll get a clean 5V signal. The pre-soldered terminal blocks and Stemma QT plugs make this a no-solder solution for adding NeoPixels easily to any device with I2C. The default I2C address is 0x60 but you can cut the bottom solder traces to change it to 0x60-0x67 inclusive.

Please note: To power NeoPixels you'll need about 10-30mA per pixel of clean 5V DC power, provided on the terminal blocks or you can just wire the 5V directly to the pixels if there's separate red and black power wires. There's no way the Stemma QT port can provide that much current so you can't just wire the pixels without an external power supply!

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
