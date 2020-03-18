# How was the case made?

Making cases is a quite challenging task. Of course you could do a box and call it a case, but I mean making a case that fits all the necesary connections and parts inside using a minimal footprint. For the ESP32 PIDFlight I designed representations of the internals with a bit of slack (1 mm extra).

![](case/images/00_lipo.PNG)

For the simple components, this is simple enough. A boundary box will suffice. However for more complex ones like the ESP32 T8 board there are some quirks to tackle.

![](case/images/01_esp32.PNG)

Anything that is exposed outside, was extended far away the physical bounds of the boards. In the image the two leds are comically large (pointing up). The sliding switch includes the two valid possible positions the physical counterpart can reach.

![](case/images/02_box.PNG)

Now, all pieces can be manually arranged and enclosed inside a box. After finishing the desired style, the internal parts are substracted to make the "holes" in the case, and finally, a *Shell* and *Split* commands are executed, resulting on two pieces. 

![](case/images/03_case.PNG)

Having the physical representations of everything inside, building standoffs and mounting pieces for the internals is easy.

![](case/images/04_quarterview.PNG)
