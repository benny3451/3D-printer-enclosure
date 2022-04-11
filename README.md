# 3D-printer-enclosure
An easy and decorative enclosure for an Ender 3 pro or printers of similar size.
====================================================

General idea
------------
I live in a small student apartment in a shared flat and therefore my 3D-printer has to be in my living/bed room. Therefore I wanted to find a solution to the noise and fume issues every 3D-printer has. The obvious answer was to build or buy an enclosure, but since there were no enclosures including filtering which met my requirements, my design choices or were just too expensive, I decided to go the DIY route. To be fair this is still  by no means a "cheap" project but I think it turned out great and so far it is meeting all the requirements I had concerning temperature, air filtration and noise cancellation. This Depository is dedicated to documenting my design and bbuild process and hopefully help you avoid some mistakes and give others inspiration to try it for themselves.

**First design in Tinkercad**

![Image](https://github.com/benny3451/3D-printer-enclosure/blob/main/pictures/Screenshot%202022-04-11%20145929.png)

Choosing parts:
--------------

After a lot of searching I settled on 30x30mm almuninium profiles for the frame. I found a seller on Ebay selling pre-cut lengths of 100mm steps. So I ordered 4x500mm, 4x600mmm and 4x700mm lengths of profile and used corner connectors to construct the frame. For the top, the back and the bottom i decided to use 8mm wood panels which I had cut to size at a local hardware store. Looking back 6mm probably would have been a better choice because the profiles inner diameter is exactly 8mm and it was quite a tight fit. The sides and the removable front panels are seethrough so I chose acryllic glas which is relatively easy to work with and readily available. My local hardware store had 6mm acryllic panels in stock and they were cut to size with no extra cost.

**Connectors**
![image](https://github.com/benny3451/3D-printer-enclosure/blob/main/pictures/714dwqiNd2L._AC_SL1500_.jpg)

**Schematic:**

![image](https://imagizer.imageshack.com/img923/3563/q3PZ7V.png)

**Stripboard Layout:**

![Image](https://imagizer.imageshack.com/img923/3299/A2sLox.png)

**Code and software**

The code running on the arduino is pretty simple. It listens for incoming serial communication, decodes the midi messages and (depending on the note value detected) switches on and of the output pins. The external software used is [hairlessMidi](https://projectgus.github.io/hairless-midiserial/#downloads), a simple yet powerful tool to send midi data via serial communication to the arduino board. Depending on what is used to generate the midi data another useful tool might be [loopMidi](https://www.tobias-erichsen.de/software/loopmidi.html). This program provides an easy way to virtually connect midi channels on your device.

**Example setup 1 (midi Keyboard):**

![image](https://imagizer.imageshack.com/img922/6168/5JUzuq.png)
The midi keyboard is selected as midi input and the serial port associated with the arduino is selected as output. Note that the displayed messages in hairlessMidi can be really useful for debugging.

**Example setup 2 (loopMidi):**  
  
![image](https://imagizer.imageshack.com/img922/2503/vIpMLo.png)
The loopMidi channel is selected as midi input and the serial port associated with the arduino is selected as output. Now the same loopMidi channel can be set as a midi output in your DAW or sequencing software. 

Sources
------
- https://www.youtube.com/watch?v=nGfqwg_r5ig  

- https://www.ti.com/lit/ds/symlink/dac0808.pdf?ts=1606046032558&ref_url=https%253A%252F%252Fwww.ti.com%252Fsitesearch%252Fdocs%252Funiversalsearch.tsp%253FsearchTerm%253Ddac0808

- https://www.ti.com/lit/ds/sdls090/sdls090.pdf?ts=1606050672047&ref_url=https%253A%252F%252Fwww.google.com%252F 

