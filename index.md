## Intro
This is a writeup of my ebike hub conversion. Building an ebike for commuting to work was something I've wanted to do for a while, and COVID was the perfect justification, as an ebike would enable me to skip the crowded bus. As of January I've put over 2000 km on the bike and my only regret is not having built it sooner. The bulk of my knowledge came from the endless-sphere and pedelecs forums, as well as the reddit ebike subreddit/discord, and of course various youtube videos. 

## Finished Product
![Finished ebike](/assets/kijiji.PNG)
The end result was a Cannondale Quick 7 converted with a Q128C 500 W hub motor and a 48 V 10.5 Ah battery custom built into a 1.5 L nalgene water bottle. 

## Overview
### Goals
I wanted my ebike to make commuting effortless while being somewhat legal, look like a normal bike, be reliable and long lasting, and of course minimize cost.

### Bike base
Bikes became in limited supply once COVID hit, and in the interests of saving money I wanted to buy used. I was checking kijiji multiple times a day for a few weeks before I found this bike, a seeminly barley used 2018 Cannondale Quick 7 which I haggled down to $350 CAD. Given the COVID market I think this was a great deal. I chose a bike with rim brakes mainly as it can be difficult to mount some hub motors with disk brakes. This is generally solvable by upgrading to larger disks (i.e. 200 mm), and in hindsight this is the one thing I might have changed, although so far the rim brakes have proven more than sufficient and of course a quality bike with disk brakes would also have increased the costs not insignificantly, particularly if I wanted hydraulics. From what I hear the main advantage of disk brakes is for wet weather, although I am generally trying to avoid the wettest or snowiest days anyway. 

### Power and speed
The legal limit for ebikes in Ontario, Canada is 32 km/hr and 500 W. I figured 500 W was a good starting point, even though all homebuilt ebikes techincally seem to be in a gray area here anyways (a requiurement is "a permanent label from the manufacturer in both English and French stating that your e-bike conforms to the federal definition of a power-assisted bicycle" - if it's homebuilt am I the manufacturer and can just put my own sticker on?). I expect my chances of being stopped are vastly lower as long as I am going close to this legal speed on a normal looking bicycle. Also, power requirements increase with the cube of speed once air resistance becomes signficant, so going above ~40 km/hr would require significantly more power. A good amount of time of my commute is also on roads with limits of 30 or 40, and facotring in time at stop signs and stop lights, the decrease in trip time would be very marginal for any increases in top speed beyond this. Going above typical max pedal bicycle speed would also likely neccesitate more involved safety gear and certainly something better than my rim brakes. Likely beefier torque arms for my aluminum frame would also have been necessary. All in all around 500 W and 40 km/hr top speed seems like a good target to maximimize the benefits/costs.

### Motor
Given the above requirements, I went with a Q128C 500 W geared rear hub for the motor. I wanted a hub motor over middrive for increased reliability and reduced wear on the drivechain. I went with a geared hub (vs direct drive) as my power requirements are modest, they can freewheel and so can still be uesd in the (albeit unlikely) event I want to use it without power, and they are smaller and lighter than gearless hubs, important for keeping the ebike looking like a normal bike. I chose the Q128C as it seemed to have a good reputation, it is freehub based so I could use it with my bike's exisitng cassette (free hubs and cassettes are higher quality than the 6-7 speed freewheels common on cheaper bikes), it is relatively stealthy/small (~128 mm diameter) and light weight (~3 kg) for its power, it's avaiable in an approrpiate winding for my torque/speed requirements, and it is a good price. I went with a rear hub as I feel the weight distribution and handling/traction improvements outweigh the increased assembly difficulty, and it's more stealthy. I laced the hub myself into an A719 rim I got used from my local bike coop.

I chose the 36 V 201 RPM configuration, run at 48 V in a 700C wheel, for the speed/torque that I wanted. There's some debate about how BMSBattery chose their designations, and the 36V 201 RPM may be the same as the 48 V 328 RPM, and neither might be actually accurate for their RPM rating. In any case mine performs as expected, giving a loaded top speed of around 40 km/hr on the flat with a full charge (50 km/hr with wheel off the ground at 100% charge), and it has plenty of starting torque even controller limited to 700 W.

Since having done this build, BMSBattery now have a Q128C with a 800 W rating available on their site for $7 more than the 500 W model, although it only appears to come in 36V 201 RPM. I'm not sure what the difference would be to allow for the extra 300 W, but I might have gone for this had it existed.

### Range and battery
My commmute to work is only about 8 km each way, so range requirements are fairly minimal by ebike standards. I still wanted a buffer in case I forgot to charge one day, or if i have an extra trip to somewhere else on top of my commute. It is also best for battery longetivity to avoid completely charging or discharging the battery, so I wanted a capacity that would let me charge to 80% and have enough power to last for potentially 2 round-trip commutes, assuming I might need to pedal a bit if I have to stretch it to two trips. 500 Wh would theoretically allow me to operate at 500 W continuous for 1 hr, and assuming a speed of 30-40 km that would give me enough for at least 2 trips, assuming 100% charge and throttle only the whole trip. Adding in some pedaling at that should be a reasonable target. At 48 V that would be around 10 aH, and so 3 parallel high capacity 3500 mAh 18650's would work nicely. My continuous power requirements of 500 W would mean only ~3.3 A per cell, so high capacity cells should handle the current requirements fine. I also looked at higher power cells which would let me use 13sp2, and fit in perhaps a smaller bottle, but then my capacity and lifecycle would be reduced. I also looked at using 21700 cells however the energy capacity would have been lower given my constraints. 

I went with LG MJ1 18650 cells as they seemed a almost perfect mix of power density (3500 MaH), current capability (10 A discharge), lifecycle, and cost. The stated discharge current would technically allow me to run at up to 10x3 = 30 A = 1500 W (30 A x 48 V), but that would probably generate a lot of heat and not be too good for the health of the battery. These high capacity cells should probably stick to around ~1 C continuous discharge. [Recent analysis](https://endless-sphere.com/forums/viewtopic.php?t=103092) has shown these MJ1 cells to be superior than the commonly used high-capcaity cells (e.g. 35E), and I was able to get them for an even cheaper price. I think more people should look into that lifecycle analysis - I think especially for commonly used high power cells such as the 30Q's which have now shown themselves to have quite poor lifecycles; they might not be used so prevalently if this was more widely known.

If I were redoing this I may have gone for 52V/14s3p for that slight bump in speed. This technically would have fit within the nalgene bottle as well based on circle packing theory, although it may have been a bit too tight. The main reason I didn't is my controller supposedly doesn't like this higher voltage and would repotedly briefly shut off power until the voltage dropped to around what the max charge should be for a 48 V nominal battery, however in practice since I only charge to 80% capacity 95% of the time, this would likley not have been a big deal at all.

I wanted my ebike to be releatively stealth and look like a normal ebike, so I wasn't a fan of the traditional hailong or shark style batteries. I decided to build it into a 1.5 L nalgene bottle, which ended up being the most time consuming part of the project. I can't recommed this unless you have significant electronics experiernce, as it is not worth it for the majority of people considering saftey, time requirements, and minimal cost savings if any. However for me the building part of this project was part of the fun, so i am glad I did it. Since I built this, Unit Pack Power on aliexpress (one of the more reputable Chinese battery builders that uses name brand batteries, if cost is a concern) has come out with some similarly specced bottle-looking batterys that might have swayed me. At the time they only had bottle-style batteries in 36 V. Being unable to lock my battery to my frame is one thing I'm missing that a commercial battery would give. It makes me a bit uneasy when locking my bike up on errands when it is just two velcro straps holding the most expensive part of my bike to the frame. At work it is in a card-access bike cage so it is not a problem 95% of the time, but it would have been nice to have the option.

### Controller
It made the most sense to order all my parts from the same place to save on shipping, I was a bit limited in my selection. I went with the S12S controller as I wanted a sine wave controller for the noise and performance benefits, and the S12S was the lowest power 48 V compatable sinewave controller from BMSBattery compatable with my motor/display. Other retailers have an S09S equivalent KT controller compatable with 48 V, but the BMS battery one is only available in square wave for some reason. It's no harm to have a larger current capability than needed, my only annoyance is the large size of the S12S case, which is apparently mostly empty anyways. I have the max current limit set to about ~14 A (~700 W) to protect the motor and battery, compared to the unlimited max of around 30 A/1500 W.

## Build
### Hub assembly
Lacing the hub into the wheel was one of the more time consuming tasks. Lacing it myself saved a lot on shipping from China, and also let me use a much higher quality rim. [This video](https://www.youtube.com/watch?v=3OialWggZJo) by Grin Technologies was most helpful. I used 12 gauge spokes from BMSBattery (I would have prefered 13 gauge but they didn't have it in the length I needed). Chinese spokes do not have the best reputation, but they have held up so far, and were far cheaper than ordering custom sized spokes from a north american company. I used a wheel lacing calculator to determine the spoke length, and went with 240 mm for my hub/rim combo. I was nervous about ordering the correct length as even with measuring there is room for error, and it doesn't take much to make the lengths unworkable, but it worked out fine in the end and everything fit properly. Without access to a proper stand I trued the wheel in the bike frame with the bike upside down.


### Battery
This was by far the most time consuming part of the project. Again, unless you know your way around electronics, I don't recommend others do this. It is safter and likely cheaper (especially after factoring in labor time) to buy a battery from a reputable company. Personally I wanted something which doens't exist commercially and I wanted the challenged of this custom build. I also have a good amount of experience with electronics.

The goal was to fit the battery inside a water bottle, to make the ebike look less like an ebike. This has been done before but with typically a much smaller number of cells or with lipo pouch cells. I haven't seen anyone build one of this size, 13s3p, or larger. The commercial ones are also the only one's I've seen in 'water bottle style' (but still not like a normal bottle) that have a  BMS, which I felt was essential for balancing and safety, but the commercial ones are also smaller capacity (Max 10s3p). I looked at a number of different bottles, steel and plastic, but the 48 oz (1.5 L) nalgene seemed the best fit, with both a large diameter and a tall enough height. I was also able to find it on clearance for $10. I cut the top off with a bandsaw and sanded both sides flat. I drilled two holes and added rubber gromits for the power wires to exit while maintaining waterproofing.

My battery configuration is 13s3p. It took a lot of thinking and sketching different layouts to figure out what would work best. This is the layout I ended up with: (image here)
Cells are grouped in parallel groups of 3, and then these are all linked in series. I designed and 3D printed custom holders to hold the batteries in this configuration: (image). The holders are designed to keep the cells spaced apart from eachother to reduce over heating potential. The design was parameterized in CAD using coodrinates for the cells based on [circle packing theory](https://en.wikipedia.org/wiki/Circle_packing_in_a_circle) so the cells would fit within the nalgene bottle with maximum spacing and room for foam wrapping. The indents around the permiter allow the wires to pass to other tiers. 

I charged and discharged (with a resistor) each individual cell so they were all at the exact same starting voltage (within 0.001 V) before assembling.

I soldered the cells directly using ? gauge wire. This is generally very much frowned upon. Everywhere will tell you to only spot weld metal strips to the cells, and that soldering cells directly will overheat and degrade them, and can potentially be very dangerous. This is not neccesarily wrong. That said, I do believe cells can be soldered with minimal risk to the cell or the person, if done properly and with the right cells. If I had access to a spot welder I would have done that, however for a one off battery build like this, it would have costed more than the battery itself. I believe the cell chemistry and construction of the LG MJ1 cells made them appropriate, and I had access to a soldering iron with a large tip to minimize time spent in contact. I had extra cells to practice with and ensure I only had to heat the cells for a minimal amount of time. Time will tell if the lifespan of my cells is reduced, but so far I haven't seen any noticable evidence that they are in any way degraded. If I were to redo my battery construction, I would still solder them, however I was using older wire which had a very stiff insulation, and the gauge I used was likely overkill, so I might instead have used either more flexible wire, or ideally soldered solid copper strips cut to the correct shape directly to the cells (similar to the strips used for spot welding, but perhaps more custom). The wire I used also ended up adding more bulk than anticipated, and after adding the BMS it was almost too tall to close - I had to use a good amount of force to close the last couple mm and then glue/tape it shut. 

I used a DALY 13s, 20 A 48 V BMS with balancing capability. I would have liked to have gone for a larger current one ideally, however I was constrained by space within my battery. I needed the BMS to fit horizontally on top of the battery, and this is the smallest appropriately sized BMS I could find, and even with this one it was borderline. The BMS wires were also soldered directly to the wires attached to the cells, which was a bit of a pain to get all the connections soldered properly. The BMS sits on the top of the back, just under the screw top.

The battey is wrapped in a layer of 3 mm EVA foam for protection, and a thicker rubber piece on the bottom for shock absorption. The wrapped battery was sealed with blue pvc heat shrink to keep everything tightly together and to match the blue water bottle, so it looks less like a battery. 

I ran this without a BMS while I was waiting for it to arrive, and checked the individual cells at arond 250 and 500 km, and in both cases the biggest cell voltage difference was 0.006 V, with most being within 0.002 V of each other. This gave me the confidence to generally charge only to below 80%, and do a full charge to 100% only every 1000 or so km, to balance the cells. 

I am using 40 amp (supposedly) anderson double pole connectors. They aren't perfect and I have had the odd issue where they dont seem to click together completly, however they work well enough and I'm not sure what would be a better connector to use. I like their well covered connections and that the connection cannot be reversed. I can already see some degredation due to arcing when unplugging the battery, so we will see how long they last. For charging I am using a standard 2.1 mm barrel socket hidden under the nalgene bottle cap, fit into a machined plastic disk that covers the BMS/battery.

I am using an XH-M604 charging controller which I attached a barrel plug and socket to so it could be connected inline between the battery and wall charger. This lets me set the upper cut-off voltage to charge the battery to only 75 or 80%. I combine this with a wall socket timer to turn the socket off after 3 hours. In total this gives me 4 independant cut-offs to avoid overcharging the battery (wall charger autocut off at 100%, BMS cutoff at 100%, XH-M604 cutoff at custom %, and wall socket timer).

### Battery bottle 'cage'
Although my battery is built into a water bottle, given that it weights x kg and is much larger than the average bicycle bottle, I needed a custom holder. There are some oversized bottle cages available, however they aren't cheap and I do not neccessarily trust their ability to hold this amount of weight. Likely one of the ones with straps might have worked fine (LiterCage? Blackburn Outpost?) but why buy something when you can make it. I machined my bottle holder out of aluminum. The top and bottom curves were machined with a boring head on a mill to match the curavuture of the nalgene bottle and down tube. A plate on the bottom was cut to shape with a bandsaw/belt sander and bolted on, to support the bottom of the bottle. Slots were milled to allow two velcro straps to secure the bottle to the holder. The holder is bolted to the downtube with the standard m5 bottle cage bolts.

### Controller mounting and Torque arms
I mounted the controller underneath my rear rack, and spray painted the controller and rack black to make it less noticable. I had to raise the rack to fit the controller between it and the rear fenders. I originally machined seperate extension pieces to raise up the rack, and used the torque arms on both sides as intended with the hose clamps, however I realized I could combine both functions into one part making things simpler and cleaner. I was not a fan of the hose clamp solution as it would scratch paint, looked bad, and I felt it was not as strong. Instead I was able to machine small brackets to connect the torque arm to the rack legs and the rack mounting holes, securing everything with m5 bolts. Considering I am only running a 500 W hub this should be plenty strong. I also replaced the rack arms with an aluminum sheet I cut and bent arms onto, in order to accommodate the increased height of the rack and also to hide the wires coming from the controller and make things look neater. The wires were run along the top and down tubes and ziptied in place.



### Parts list and costs

| Part | Cost | Source | Description |
|-------|--------|---------|---------|
| 2018 Cannondale Quick 7 | $350 CAD | Kijiji | Midnight blue, 24 speed (11-32), Altus/Acera |
| Q128C-135mm 500W CST Rear Driving EBike Hub Motor | $112.00 USD | BMSBattery | Voltage: 36V RPM: 201 |
| S12S 500Watts Torque Simulation Sine Wave Controller | $34.00 USD | BMSBattery | 30 A max current |
| A Pair of EBike Torque Arm - Size : M12 | $15.00 USD | BMSBattery | Old gen 1 style not typically recomended, but for 500 W and with two of them it shouldn't be an issue |
| Spoke Wrench | $1 USD | BMSBattery | For lacing hub |
| CASSETTE REMOVER And Install TOOL	 | $5.00 USD | BMSBattery | For transfering cassette from original wheel to hub |
| S-LCD6 LCD Meter for S-Series Controllers	| $30.00 USD | BMSBattery | I think this vertical style looks nicer than the seemingly more common S-LCD3 |
| Bicycle B B Axle Wrench Tools | $3.00 USD | BMSBattery | For installing PAS |
| Cotterless Crank Tool	 | $1.60 USD | BMSBattery | For installing PAS |
| PAS--Pulse Padel Assistant Sensor With 12 PCS Magnets | $5.00 USD | BMSBattery | I had some concerns about compatability with my controller, but it works fine and I think looks cleaner and more subtle than the other styles |
| 5 pcs 12G Stainless Steel Spoke with a Brass Nipple (x 9) | $9.00 USD | BMSBattery | 240 mm length; Maybe not the best quality but they worked |
| Dual Hall Sensor 12 Signals Easy Assembling PAS | $4.00 USD | BMSBattery | Not used, backup in case the other one didn't work |
| Thumb Level Throttle without Handle | $4.00 USD | BMSBattery | The throttle I ended up using, mounted backwards on the left. An actual left handed one would probably work better. |
| Anderson Double Poles Connector - Current Selection : 40Amps	(x 3) | $4.50 USD | BMSBattery |  |
| Left Handed Half Twist Throttle | $4.00 USD | BMSBattery | Seems to be a fan favorite but I prefered the thumb throttle |
| 1 meter PVC heat shrink tube - Large - Half Perimeter(mm) : 160	 | $1.00 USD | BMSBattery | Battery wrapping |
| 1 meter PVC heat shrink tube - Large - Half Perimeter(mm) : 143	 | $1.00 USD | BMSBattery | Battery wrapping |
| S120M MCU OLED Display LiFePo4/Li-Ion Battery Smart Charger - Power : 120W | $22.00 USD | BMSBattery | Smart battery charger |
| HWBS - Hidden Wire Brake Sensor 1pcs | $6.00 USD | BMSBattery | Works pretty well, used just on rear brake (don't have exposed cable on front brake) |
| 3 mm EVA foam | $5.92 CAD | Michael's |  |
| 42x LG MJ1 18650 cells | $264.60 CAD | 18650Canada | Worked out to $6.30 CAD/cell |
| XTAR MC1S Charger | $6.08 CAD | 18650Canada | Used to bring all cells to same starting voltage (3.7 V) (also used a big resistor to discharge if needed)|
| BMSBattery fedex shipping + duties | $99.93 USD + 52.72 CAD| Fedex | Lacing hub myself kept shipping costs down |
| 3D printed battery cell holders | $55.00 CAD |  | Printed in ABS using 3D printer at work, just paid for materials |
| 48 oz Nalgene bottle | $11.22 CAD | Candian Tire |  |
| Front headlight | $8.11 CAD | Aliexpress |  |
| Rear taillight | $13.44 CAD | Aliexpress |  |
| 2x pushbutton switches, 16 mm LED latching, red and white  | $3.52 CAD | Aliexpress | For controlling lights. Accidentally blew one up.. |
| XH-M604 Battery charging controller with case | $13.46 CAD | Aliexpress | Cuts off charging at set voltage |
| Daly 13s BMS | $23.17 CAD | Aliexpress |  |
| A719 rim | $20.00 CAD | Local bike coop |  |
| Front and rear fenders | $20.00 CAD | Local bike coop |  |
| Total, CAD | $1354 CAD |  | Converting all to CAD  |
| Total, USD | $967 USD |  | Converting all to USD |

Unforunately I apparenlty decided to build this at a time when the exchange rate was one of the worst it been in a couple decades (~1.4 CAD to USD), so that added to the cost. The total ended up being split pretty evenly three ways between the battery, the bike, and the motor/other electronics. I'm happy with what I got for the end price, I definetly tried to do things as cheaply as possible while still being quality, meaning ordering most parts from China and waiting for shipping, and doing the labor intenstive parts myself. I don't think I could find a similarly specced prebuilt ebike for this price, although they are getting close.

## Appendix
### References

### Excel sheet stuff
These are just some rough notes I took during my research process.
## Retailers

| Retailer | Products/notes | 
|-------|--------|
| ebikelifes |	bad rep and no longer exists? Now pswpower |					
| topbikekit |	q128c (akm-128cst) and 260 rpm option. Shipping ~200 for just wheel	 |				
| pswpower | (g311 for 155, free shipping?)	 |					
| ebikes.ca |	G310/G311, high quality but high price	 |				
| greenbikekit.com |	q100cst, 100r,bpm,  swxh. Crazy shipping?? (285 for wheel kit only)	 |				
| bmsbattery.com |	q100, q128 |					
| cnebikes | |
| ebikeling |	shipping 107, total 366 for 700c 36v 500w geared rear waterproof kit..   Outrider standard? Good for 20 mph on throttle @ 36v, ~24 @ 48V	 |				

## Alternate hub motors
| Motor | Notes |
|----|----|
| Q100 | 	called cute by bmsbattery	17 amps to get best out of it				|


|	Q100H |	more tourqe, frewheel body only. Ranges = low (201rpm@36), mid (260) high (328). Should use mid in 26". 260@36v=32kph no load, ~40kph @48v (no load). 260@20A ~23 mph top speed? Realistic 32 kph top speed (26" wheel 13s lipo = 55v off charger)			|
|	Q128 |			|		
|	Q128H |	more tourqe, but frewheel body only. Get if 7 or less gears at the back. 800w rather than 500 with the c			|
|	Q128C |	casscette/freehub, narrower (to make room for cascette) and less power than the H. 36v 201 rpm version at 48V bat (at 52V) with 26" wheels = 22 mph on flat with steady pedaling (19 w/o pedal??). Supposedly 36v201rpm is same as 48v328 rpm and is actually 36v260rpm "I'm using the 36v 201 rpm one at 48v with a 14 amp sine wave KT controller. I get a top speed on the road of about 38km/h with 26"wheels." similar size to g310	|
|Q100C |	same as GBK 100CST	not available In mid speed?		201rpm version only does about 15 mph at 10s (36v?) (throttle only: 201@36v=28kph, @48v=35kph)		requires special cassete tool and 8 gear cassette freewheel (from donor bike)?|
|	BPM2 |	bigger and more power than 128				|
|	mxus mini |	between q100 and q128 in size				|
|	mxus xf15c |	158mm outer diam (vs 144 for q128c). 150 ships free from pswpoer?			|
|bmc |	expensive? Bigger and faster (30mph)				|
|bafang	SWXH |	(SWSK is front version)	similar to Q100, slightly bigger and more torqy, bit noisier, avial in mid speed. Greenbikekit or elifebikes. On road @ 48v without pedaling = 21 mph, 23 with pedaling (20 amps? Quieter at 14)			|
|	Bafang "8-Fun" SWX02 |	Ebikeling 500W 	comparable to q128	24 mph at 48v, 20 at 36v		|
|	bafang cst |	500w. 2x price on bmsbattery							|
|	xiongda XD |	2-speed, more torque but otherwise worse than q128			|
|	xiongda ytw-06 |	even smaller than q100			|
|	mac |	bigger than q128, more power				|
						
            
## Quotes regarding BMSBattery Q128C winding options
Collected from endless-sphere/pedelecs:

"I'm pretty sure that the 201 rpm 36v Q128c is actually 260 rpm and it's identical to the 48v 328 rpm Q128C, i.e. they're the same motor."

"By all accounts, the 36v 201 rpm and the 48v 328 rpm are in fact the same motor apart from the label, so you can take your pick. I have the 36v 201 rpm at 48v in a 26" wheel. I have it limited to 15.5 mph, but even at that speed, it seems to be pretty efficient. It has plenty of torque, but I have a feeling that it would work better in a 26" wheel than 700C."

"how 201rpm at 36V equates to 328 at 48V. I make it roughly 268"

"Simple. The 201 rpm 36v motor is not 201 rpm. It's 260 rpm!"

"I have a 36v 201 rpm Q128c in 700c wheel, and as far as I can tell according to the ebikes.ca simulator, it spins true at around 260 rpm at 48V. I've never tried the 48V 320rpm model."

"The Q128 328 rated @ 48 Volts is, in fact a 260 version were it rated @ 36 Volts."

"Lets get one thing straight: A Q100 at 15 amps will make more or less the same power as a Q128 at 15 amps."

"48v and 15A is about as high as you can go on a Q100, but you can go to at least 20A with a Q128."

"How a hub-motor behaves, depends on the controller. If you don't set a speed limit, the power will ramp down and fade out as it approaches maximum rpm.
There are basically 3 flavours of Qxxx motors:
201 rpm = 15 mph (real OTR speed)
260 rpm = 19 mph
328 rpm = 24 mph"

"When you run a 36v 201 rpm at 48v, it becomes a 260 rpm one, and a 260 rpm one becomes a 48v one."

"BMSB listing details are often incorrect. We know that the 201 rpm 36v Q128C is actually 260 rpm."

## Battery calculations

|Cell name |30q|	sanyo GA 3450|	35e|	40t|	MNKE| 	sanyo| 	LG MJ1|	25r|	18650bd|
|---|---|---|---|---|---|---|---|---|---|
|Cell type|	18650	|18650	|18650	|21700	|26650	|20700B	|18650	|18650	|18650|
|18650 canada price/cell (CAD)|	7.85|	8.6|	7.6|	10|	5.85|	9.85|	7|	5.95|	6.8|
|1p capacity (Ah)|	3|	3.5|	3.5|	4|	5|	4.25|	3.5|	2.5|	3.18|
|cost (CAD)|	102.05|	111.8|	98.8|	130|	76.05|	128.05|	91|	77.35|	88.4|
|2p capacity (Ah)	|6|	7|	7|	8|	10|	8.5|	7|	5|	6.36|
|cost (CAD)|	204.1|	223.6|	197.6|	260|	152.1|	256.1|	182|	154.7|	176.8|
|3p capacity (Ah)	|9|	10.5|	10.5|	12|	15|	12.75|	10.5|	7.5|	9.54|
|cost (CAD)|	306.15|	335.4|	296.4|	390|	228.15|	384.15|	273|	232.05|	265.2|
|continuous current per cell (A)|	15|	10|	8|	30|	20|	15 (75d cut)|	10|	20|	10|
|CAD/Ah|	34.01666667|	31.94285714|	28.22857143|	32.5|	15.21|	30.12941176|	26|	30.94|	27.79874214|


