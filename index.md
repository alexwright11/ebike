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
The legal limit for ebikes in Ontario, Canada is 32 km/hr and 500 W. I figured 500 W was a good starting point, even though all homebuilt ebikes techincally seem to be in a gray area here anyways (a requiurement is "a permanent label from the manufacturer in both English and French stating that your e-bike conforms to the federal definition of a power-assisted bicycle" - if it's homebuilt am I the manufacturer and can just put my own sticker on?). I expect my chances of being stopped are vastly lower as long as I am going close to this legal speed on a normal looking bicycle. Also, power requirements increase with the cube of speed once air resistance becomes signficant, so going above ~40 km/hr would require significantly more power. A good amount of time of my commute is also on roads with limits of 30 or 40, and facotring in time at stop signs and stop lights, the decrease in trip time would be very marginal for any increases in top speed beyond this. Going above typical max pedal bicycle speed would also likely neccesitate more involved safety gear and certainly something better than my rim brakes. All in all around 500 W and 40 km/hr top speed seems like a good target to maximimize the benefits/costs.

### Motor
Given the above requirements, I went with a Q128C 500 W geared rear hub for the motor. I chose this motor as it seemed to have a good reputation, it is freehub based so I could use it with my bike's exisitng cassette (free hubs and cassettes are higher quality than the 6-7 speed freewheels common on cheaper bikes), it is relatively stealthy/small (~128 mm diameter) and light weight (3 kg) for its power, it's avaiable in an approrpiate winding for my torque/speed requirements, and it is a good price. I went with a rear hub as I feel the weight distribution and handling/traction improvements outweigh the increased assembly difficulty. I laced the hub myself into an A719 rim I got used from my local bike coop.

### Range and battery
My commmute to work is only about 8 km each way, so range requirements are fairly minimal by ebike standards. I still wanted a buffer in case I forgot to charge one day, or if i have an extra trip to somewhere else on top of my commute. It is also best for battery longetivity to avoid completely charging or discharging the battery, so I wanted a capacity that would let me charge to 80% and have enough power to last for potentially 2 round-trip commutes, assuming I might need to pedal a bit if I have to stretch it to two trips. 500 Wh would theoretically allow me to operate at 500 W continuous for 1 hr, and assuming a speed of 30-40 km that would give me enough for at least 2 trips, assuming 100% charge and throttle only the whole trip. Adding in some pedaling at that should be a reasonable target. At 48 V that would be around 10 aH, and so 3 parallel high capacity 3500 mAh 18650's would work nicely. My continuous power requirements of 500 W would mean only ~3.3 A per cell, so high capacity cells should handle the current requirements fine.

I went with LG MJ1 cells as they seemed a almost perfect mix of power density (3500 MaH), current capability (10 A discharge), lifecycle, and cost. The stated discharge current would technically allow me to run at up to 10x3 = 30 A = 1500 W (30 A x 48 V), but that would probably generate a lot of heat and not be too good for the health of the battery. These high capacity cells should probably stick to around ~1 C continuous discharge. [Recent analysis](https://endless-sphere.com/forums/viewtopic.php?t=103092) has shown these MJ1 cells to be superior than the commonly used high-capcaity cells (e.g. 35E), and I was able to get them for an even cheaper price. I think more people should look into that lifecycle analysis - I think especially for commonly used high power cells such as the 30Q's which have now shown themselves to have quite poor lifecycles; they might not be used so prevalently if this was more widely known.

If I were redoing this I may have gone for 52V/14s3p for that slight bump in speed. The reason I didn't is my controller supposedly doesn't like this higher voltage and would repotedly briefly shut off power until the voltage dropped to around what the max charge should be for a 48 V nominal battery, however in practice since I only charge to 80% capacity 95% of the time, this would likley not have been a big deal at all.

I wanted my ebike to be releatively stealth and look like a normal ebike, so I wasn't a fan of the traditional hailong or shark style batteries. I decided to build it into a 1.5 L nalgene bottle, which ended up being the most time consuming part of the project. I can't recommed this unless you have significant electronics experiernce, as it is not worth it for the majority of people considering saftey, time requirements, and minimal cost savings if any. However for me the building part of this project was part of the fun, so i am glad I did it.

### Controller
It made the most sense to order all my parts from the same place to save on shipping, I was a bit limited in my selection. I went with the S12S controller as I wanted a sine wave controller for the noise and performance benefits, and the S12S was the lowest power 48 V compatable sinewave controller from BMSBattery compatable with my motor/display. Other retailers have an S09S equivalent KT controller compatable with 48 V, but the BMS battery one is only available in square wave for some reason. It's no harm to have a larger current capability than needed, my only annoyance is the large size of the S12S case, which is apparently mostly empty anyways. I have the max current limit set to about ~14 A (~700 W) to protect the motor and battery, compared to the unlimited max of around 30 A/1500 W.

## Build
###

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
