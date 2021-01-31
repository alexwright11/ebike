## Intro

This is a writeup of my ebike hub conversion. Building an ebike for commuting to work was something I've wanted to do for a while, and COVID was the perfect justification, as an ebike would enable me to skip the crowded bus. As of January I've put over 2000 km on the bike and my only regret is not having built it sooner. The bulk of my knowledge came from the endless-sphere and pedelecs forums, as well as the reddit ebike subreddit/discord, and of course various youtube videos. 

## Finished Product
- photo here -
The end result was a Cannondale Quick 7 converted with a Q128C 500 W hub motor and a 48 V 10.5 Ah battery custom built into a 1.5 L nalgene water bottle. 

## Overview
### Goals
I wanted my ebike to make commuting effortless while being somewhat legal, look like a normal bike, be reliable and long lasting, and of course minimize cost.

### Bike base
Bikes became in limited supply once COVID hit, and in the interests of saving money I wanted to buy used. I was checking kijiji multiple times a day for a few weeks before I found this bike, a seeminly barley used 2018 Cannondale Quick 7 which I haggled down to $350 CAD. Given the COVID market I think this was a great deal. I chose a bike with rim brakes mainly as it can be difficult to mount some hub motors with disk brakes. This is generally solvable by upgrading to larger disks (i.e. 200 mm), and in hindsight this is the one thing I might have changed, although so far the rim brakes have proven more than sufficient and of course a quality bike with disk brakes would also have increased the costs not insignificantly, particularly if I wanted hydraulics. From what I hear the main advantage of disk brakes is for wet weather, although I am generally trying to avoid the wettest or snowiest days anyway. 

### Power and speed
The legal limit for ebikes in Ontario, Canada is 32 km/hr and 500 W. I figured 500 W was a good starting point, even though all homebuilt ebikes techincally seem to be in a gray area here anyways (a requiurement is "a permanent label from the manufacturer in both English and French stating that your e-bike conforms to the federal definition of a power-assisted bicycle" - if it's homebuilt am I the manufacturer and can just put my own sticker on?). I expect my chances of being stopped are vastly lower as long as I am going close to this legal speed on a normal looking bicycle. Also, power requirements increase with the cube of speed once air resistance becomes signficant, so going above ~40 km/hr would require significantly more power. A good amount of time of my commute is also on roads with limits of 30 or 40, and facotring in time at stop signs and stop lights, the decrease in trip time would be very marginal for any increases in top speed beyond this. Going above typical max pedal bicycle speed would also likely neccesitate more involved safety gear and certainly something better than my rim brakes. Likely beefier torque arms for my aluminum frame would also have been necessary. All in all around 500 W and 40 km/hr top speed seems like a good target to maximimize the benefits/costs.

### Motor
Given the above requirements, I went with a Q128C 500 W geared rear hub for the motor. I wanted a hub motor over middrive for increased reliability and reduced wear on the drivechain. I went with a geared hub as my power requirements are modest, and they are smaller and lighter than gearless hubs, important for keeping the ebike bike looking. I chose the Q128C as it seemed to have a good reputation, it is freehub based so I could use it with my bike's exisitng cassette (free hubs and cassettes are higher quality than the 6-7 speed freewheels common on cheaper bikes), it is relatively stealthy/small (~128 mm diameter) and light weight (3 kg) for its power, it's avaiable in an approrpiate winding for my torque/speed requirements, and it is a good price. I went with a rear hub as I feel the weight distribution and handling/traction improvements outweigh the increased assembly difficulty, and it's more stealthy. I laced the hub myself into an A719 rim I got used from my local bike coop.

I chose the 36 V 201 RPM configuration, run at 48 V in a 700C wheel, for the speed/torque that I wanted. There's some debate about how BMSBattery chose their designations, and the 36V 201 RPM may be the same as the 48 V 328 RPM, and neither might be actually accurate for their RPM rating. In any case mine performs as expected, giving a loaded top speed of around 40 km/hr on the flat with a full charge (50 km/hr with wheel off the ground at 100% charge), and it has plenty of starting torque even controller limited to 700 W.

Since having done this build, BMSBattery now have a Q128C with a 800 W rating available on their site for $7 more than the 500 W model, although it only appears to come in 36V 201 RPM. I'm not sure what the difference would be to allow for the extra 300 W, but I might have gone for this had it existed.

### Range and battery
My commmute to work is only about 8 km each way, so range requirements are fairly minimal by ebike standards. I still wanted a buffer in case I forgot to charge one day, or if i have an extra trip to somewhere else on top of my commute. It is also best for battery longetivity to avoid completely charging or discharging the battery, so I wanted a capacity that would let me charge to 80% and have enough power to last for potentially 2 round-trip commutes, assuming I might need to pedal a bit if I have to stretch it to two trips. 500 Wh would theoretically allow me to operate at 500 W continuous for 1 hr, and assuming a speed of 30-40 km that would give me enough for at least 2 trips, assuming 100% charge and throttle only the whole trip. Adding in some pedaling at that should be a reasonable target. At 48 V that would be around 10 aH, and so 3 parallel high capacity 3500 mAh 18650's would work nicely. My continuous power requirements of 500 W would mean only ~3.3 A per cell, so high capacity cells should handle the current requirements fine.

I went with LG MJ1 cells as they seemed a almost perfect mix of power density (3500 MaH), current capability (10 A discharge), lifecycle, and cost. The stated discharge current would technically allow me to run at up to 10x3 = 30 A = 1500 W (30 A x 48 V), but that would probably generate a lot of heat and not be too good for the health of the battery. These high capacity cells should probably stick to around ~1 C continuous discharge. [Recent analysis](https://endless-sphere.com/forums/viewtopic.php?t=103092) has shown these MJ1 cells to be superior than the commonly used high-capcaity cells (e.g. 35E), and I was able to get them for an even cheaper price. I think more people should look into that lifecycle analysis - I think especially for commonly used high power cells such as the 30Q's which have now shown themselves to have quite poor lifecycles; they might not be used so prevalently if this was more widely known.

If I were redoing this I may have gone for 52V/14s3p for that slight bump in speed. The reason I didn't is my controller supposedly doesn't like this higher voltage and would repotedly briefly shut off power until the voltage dropped to around what the max charge should be for a 48 V nominal battery, however in practice since I only charge to 80% capacity 95% of the time, this would likley not have been a big deal at all.

I wanted my ebike to be releatively stealth and look like a normal ebike, so I wasn't a fan of the traditional hailong or shark style batteries. I decided to build it into a 1.5 L nalgene bottle, which ended up being the most time consuming part of the project. I can't recommed this unless you have significant electronics experiernce, as it is not worth it for the majority of people considering saftey, time requirements, and minimal cost savings if any. However for me the building part of this project was part of the fun, so i am glad I did it. Since I built this, Unit Pack Power on aliexpress (one of the more reputable Chinese battery builders that uses name brand batteries, if cost is a concern) has come out with some similarly specced bottle-looking batterys that might have swayed me. At the time they only had bottle-style batteries in 36 V. Being unable to lock my battery to my frame is one thing I'm missing that a commercial battery would give. It makes me a bit uneasy when locking my bike up on errands when it is just two velcro straps holding the most expensive part of my bike to the frame. At work it is in a card-access bike cage so it is not a problem 95% of the time, but it would have been nice to have the option.

### Controller
It made the most sense to order all my parts from the same place to save on shipping, I was a bit limited in my selection. I went with the S12S controller as I wanted a sine wave controller for the noise and performance benefits, and the S12S was the lowest power 48 V compatable sinewave controller from BMSBattery compatable with my motor/display. Other retailers have an S09S equivalent KT controller compatable with 48 V, but the BMS battery one is only available in square wave for some reason. It's no harm to have a larger current capability than needed, my only annoyance is the large size of the S12S case, which is apparently mostly empty anyways. I have the max current limit set to about ~14 A (~700 W) to protect the motor and battery, compared to the unlimited max of around 30 A/1500 W.

## Build
### Hub assembly
Lacing the hub into the wheel was one of the more time consuming tasks. Lacing it myself saved a lot on shipping from China, and also let me use a much higher quality rim. [This video](https://www.youtube.com/watch?v=3OialWggZJo) by Grin Technologies was most helpful. I used 12 gauge spokes from BMSBattery (I would have prefered 13 gauge but they didn't have it in the length I needed). Chinese spokes do not have the best reputation, but they have held up so far, and were far cheaper than ordering custom sized spokes from a north american company. I used a wheel lacing calculator to determine the spoke length, and went with 240 mm for my hub/rim combo. I was nervous about ordering the correct length as even with measuring there is room for error, and it doesn't take much to make the lengths unworkable, but it worked out fine in the end and everything fit properly. Without access to a proper stand I trued the wheel in the bike frame with the bike upside down.


### Battery
This was by far the most time consuming part of the project. Again, unless you know your way around electronics, I don't recommend others do this. It is safter and likely cheaper (especially after factoring in labor time) to buy a battery from a reputable company. Personally I wanted something which doens't exist commercially and I wanted the challenged of this custom build. I also have a good amount of experience with electronics.

My battery configuration is 13s3p. It took a lot of thinking and sketching different layouts to figure out what would work best. This is the layout I ended up with: (image here)
Cells are grouped in parallel groups of 3, and then these are all linked in series. I designed and 3D printed custom holders to hold the batteries in this configuration: (image). The holders are designed to keep the cells spaced apart from eachother to reduce over heating potential. The design was parameterized in CAD using coodrinates for the cells based on [circle packing theory](https://en.wikipedia.org/wiki/Circle_packing_in_a_circle) so the cells would fit within the nalgene bottle with maximum spacing and room for foam wrapping. The indents around the permiter allow the wires to pass to other tiers.

I charged and discharged (with a resistor) each individual cell so they were all at the exact same starting voltage (within 0.001 V) before assembling.

I soldered the cells directly using ? gauge wire. This is generally very much frowned upon. Everywhere will tell you to only spot weld metal strips to the cells, and that soldering cells directly will overheat and degrade them, and can potentially be very dangerous. This is not neccesarily wrong. That said, I do believe cells can be soldered with minimal risk to the cell or the person, if done properly and with the right cells. If I had access to a spot welder I would have done that, however for a one off battery build like this, it would have costed more than the battery itself. I believe the cell chemistry and construction of the LG MJ1 cells made them appropriate, and I had access to a soldering iron with a large tip to minimize time spent in contact. I had extra cells to practice with and ensure I only had to heat the cells for a minimal amount of time. Time will tell if the lifespan of my cells is reduced, but so far I haven't seen any noticable evidence that they are in any way degraded. If I were to redo my battery construction, I would still solder them, however I was using older wire which had a very stiff insulation, and the gauge I used was likely overkill, so I might instead have used either more flexible wire, or ideally soldered solid copper strips cut to the correct shape directly to the cells (similar to the strips used for spot welding, but perhaps more custom). The wire I used also ended up adding more bulk than anticipated, and after adding the BMS it was almost too tall to close - I had to use a good amount of force to close the last couple mm and then glue/tape it shut. 

I used a DALY 13s, 20 A 48 V BMS with balancing capability. I would have liked to have gone for a larger current one ideally, however I was constrained by space within my battery. I needed the BMS to fit horizontally on top of the battery, and this is the smallest appropriately sized BMS I could find, and even with this one it was borderline. The BMS wires were also soldered directly to the wires attached to the cells, which was a bit of a pain to get all the connections soldered properly. 

The battey is wrapped in a layer of 3 mm EVA foam for protection, and a thicker rubber piece on the bottom for shock absorption. The wrapped battery was sealed with blue pvc heat shrink to keep everything tightly together and to match the blue water bottle, so it looks less like a battery. 

I checked the individual cells at arond 250 and 500 km, and in both cases the biggest cell voltage difference was 0.006 V, with most being within 0.002 V of each other. Based on this I generally charge only to below 80%, and do a full charge to 100% only every 1000 or so km, to balance the cells.

I am using 40 amp (supposedly) anderson double pole connectors. They aren't perfect and I have had the odd issue where they dont seem to click together completly, however they work well enough and I'm not sure what would be a better connector to use. I like their well covered connections and that the connection cannot be reversed. I can already see some degredation due to arcing when unplugging the battery, so we will see how long they last. For charging I am using a standard 2.1 mm barrel socket hidden under the nalgene bottle cap, fit into a machined plastic disk that covers the BMS/battery.

### Battery bottle 'cage'
Although my battery is built into a water bottle, given that it weights x kg and is much larger than the average bicycle bottle, I needed a custom holder. There are some oversized bottle cages available, however they aren't cheap and I do not neccessarily trust their ability to hold this amount of weight. Likely one of the ones with straps might have worked fine (LiterCage? Blackburn Outpost?) but why buy something when you can make it. I machined my bottle holder out of aluminum. The top and bottom curves were machined with a boring head on a mill to match the curavuture of the nalgene bottle and down tube. A plate on the bottom was cut to shape with a bandsaw/belt sander and bolted on, to support the bottom of the bottle. Slots were milled to allow two velcro straps to secure the bottle to the holder. The holder is bolted to the downtube with the standard m5 bottle cage bolts.

### Controller mounting and Torque arms
I mounted the controller underneath my rear rack, and spray painted the controller and rack black to make it less noticable. I had to raise the rack to fit the controller between it and the rear fenders. I originally machined seperate extension pieces to raise up the rack, and used the torque arms on both sides as intended with the hose clamps, however I realized I could combine both functions into one part making things simpler and cleaner. I was not a fan of the hose clamp solution as it would scratch paint, looked bad, and I felt it was not as strong. Instead I was able to machine small brackets to connect the torque arm to the rack legs and the rack mounting holes, securing everything with m5 bolts. Considering I am only running a 500 W hub this should be plenty strong. I also replaced the rack arms with a custom aluminum sheet I cut and bent arms onto, in order to accomidate the increase height of the rack and also to hide the wires coming from the controller and make things more stealth.



### Parts list and costs

| Part | Cost (CAD) | Source | Description |
|-------|--------|---------|---------|
| 2018 Cannondale Quick 7 | $350 CAD | Kijiji | Midnight blue, 24 speed (11-32), Altus/Acera |
| Q128C-135mm 500W CST Rear Driving EBike Hub Motor | $112 USD | BMSBattery | Voltage: 36V RPM: 201 |
| S12S 500Watts Torque Simulation Sine Wave Controller | $34 USD | BMSBattery | 30 A max current |
| A Pair of EBike Torque Arm - Size : M12 | $15 USD | BMSBattery | Old gen 1 style not typically recomended, but for 500 W and with two of them it shouldn't be an issue |
| Spoke Wrench | $1 USD | BMSBattery | For lacing hub |
| CASSETTE REMOVER And Install TOOL	 | $5 USD | BMSBattery | For transfering cassette from original wheel to hub |
| S-LCD6 LCD Meter for S-Series Controllers	| $30 USD | BMSBattery | I think this vertical style looks nicer than the seemingly more common S-LCD3 |
| Bicycle B B Axle Wrench Tools | $3 USD | BMSBattery | For installing PAS |
| Cotterless Crank Tool	 | $1.60 USD | BMSBattery | For installing PAS |
| PAS--Pulse Padel Assistant Sensor With 12 PCS Magnets | $5.00 | BMSBattery | I had some concerns about compatability with my controller, but it works fine and I think looks cleaner and more subtle than the other styles |
| 5 pcs 12G Stainless Steel Spoke with a Brass Nipple (x 9) | $9 USD | BMSBattery | 240 mm length; Maybe not the best quality but they worked |
| Dual Hall Sensor 12 Signals Easy Assembling PAS | $4.00 USD | BMSBattery | Not used, backup in case the other one didn't work |
| Thumb Level Throttle without Handle | $4.00 | BMSBattery | The throttle I ended up using, mounted backwards on the left. An actual left handed one would probably work better. |
| Anderson Double Poles Connector - Current Selection : 40Amps	(x 3) | $4.50 | BMSBattery |  |
| Left Handed Half Twist Throttle | $4.00 | BMSBattery | Seems to be a fan favorite but I prefered the thumb throttle |
| 1 meter PVC heat shrink tube - Large - Half Perimeter(mm) : 160	 | $1 USD | BMSBattery | Battery wrapping |
| 1 meter PVC heat shrink tube - Large - Half Perimeter(mm) : 143	 | $1 USD | BMSBattery | Battery wrapping |
| S120M MCU OLED Display LiFePo4/Li-Ion Battery Smart Charger - Power : 120W | $22 USD | BMSBattery | Smart battery charger |
| 3 mm EVA foam | $ | Michael's |  |
| 42x LG MJ1 18650 cells | $264.60 CAD | 18650Canada | Worked out to $6.30 CAD/cell |
| XTAR MC1S Charger | $6.08 CAD | 18650Canada | Used to bring all cells to same starting voltage (3.7 V) (also used a big resistor to discharge if needed)|
| HWBS - Hidden Wire Brake Sensor 1pcs | $6 | BMSBattery | Works pretty well, used just on rear brake (don't have exposed cable on front brake) |
| BMSBattery fedex shipping + duties | $99.93 USD + 52.72 CAD| Fedex | Lacing hub myself kept shipping costs down |
| 3D printed battery cell holders | $55 CAD |  | Printed in ABS using 3D printer at work, just paid for materials |
| 48 oz Nalgene bottle | $11.22 CAD | Candian Tire |  |
| Front headlight | $8.11 CAD | Aliexpress |  |
| Rear taillight | $13.44 CAD | Aliexpress |  |
| Battery charging controller with case | $10.79 CAD | Aliexpress | Cuts off charging at set voltage |
| Daly 13s BMS | $23.17 CAD | Aliexpress |  |


## Appendix
### References

### Excel sheet stuff





ou can use the [editor on GitHub](https://github.com/alexwright11/ebike/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/alexwright11/ebike/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
