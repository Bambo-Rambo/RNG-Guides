# Gen 6 Horde Encounter RNG (Not 100% complete)

### [Original Page](https://github.com/Bambo-Rambo/RNG-Guides/wiki/Horde-Encounter-RNG---Generation-6)

# What you will need:
# Tools
* [3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases/tag/1.0.5)
* [Pcalc for 3DS](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) or [CitraRNG for Citra Emulator](https://github.com/Admiral-Fish/CitraRNG/releases/tag/v3.1.0)
* [Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder) (Optional)

# In game

* Honey to trigger the horde. Sweet scent works as well but its setup is not supported in the existing tools

* Shiny Charm (Highly recommended if going for shinies)

* A Pokemon with the Synchronize ability in the first slot if you want a specific nature

* Maximizing the memories of all Pokemon in your party is recommended

* Some experience with RNG manipulation in generation 6

* This guide supposes that you already have understood what TinyMT is and why does it matter

# Getting Started

Select the "Horde" Category in the tool and use the reseed method until you find a frame that satisfies you. Search for something that has the desired IVs and shininess only. The rest (sync, slot, HA etc) will be manipulated later. If you are planning on syncing the nature, check the "Assume Synced" box to get an idea of how the target Pokemon will be.

![](https://i.imgur.com/J1QWdKw.png)

I will be aiming for a Jolly shiny Starly at Route 11. I also want it to have its hidden ability so the gender may be the opposite but we will check it later. We also need to check which of these 15 frames to aim for which is something we will do later as well.


# Setting up the tool - Calibrating the delay

First, we need to make a "test" attempt to find our delay.

Μake sure that you have the correct version selected (XY or ORAS) in the main window of the tool otherwise you are going to get wrong results. Then open the Tiny Timeline Tool and put the exact number of Pokemon in your party. If you are doing this in caves, check the "Cave" box.

![](https://i.imgur.com/MERXKVz.png)

The nice thing about Horde RNG, is that we can first set up the TinyMT to guarantee the slot, sync and HA, and then wait inside the bag until we reach our target frame then use the Honey. Let's see how:

In game, press the X button to open the menu and calibrate the TinyMT. If you are using the [NTR helper](https://github.com/wwwwwwzx/3DSRNGTool/wiki/NTR-Helper-Usage), press "Calibrate" and it will do it for you. 

Scroll down a bit (or use Tiny Finder to filter the results to your preference) until you find the desired index. I will be using a Starly horde to calibrate the delay so I am looking for a slot 3 (Starly) index. You can use any index for testing though.

![](https://i.imgur.com/yC4cBDN.png)

So index 10 is the one I need to use honey at, in order to get a Starly. As we can understand, for that index, the nature will sync and neither of the 5 Starlys will have their hidden ability (doesn't matter since I will only calibrate the delay this time).

In order to land at index 10, what I am going to do is enter the bag at index 8. Remember that entering the bag, causes one advancement and then freezes the TinyMT until you manually advance it again.

![](https://i.imgur.com/nV48Fmi.png)

At index 9, I only need one more advancement. A relible way to do this, is checking the summary of one of your Pokemon once. Select one from your party with 4 moves and attempt to teach it a new move. When prompted to replace an old one, reject it (replacing it will advance the TinyMT by more than 1 so don't do it). Also don't stay in the summary screen for too long because it will keeping advancing constantly.

Other ways of advancing the TinyMT state inside the bag include:

* Turning on/off the Exp Share advances by 3 for every Pokemon in your party
* Giving one of your Pokemon a held item, advances by 3 (sometimes by 4).

![](https://i.imgur.com/t2Z769i.png)

We are now at index 10 ready to get our Starly horde. **Right click on it and set it as current status**. Then go to the main window and click search. The following text will appear and confirm the characteristics of your current index. If it shows different results from the ones you are expecting, double check everything and fix the error. This is important because the tool needs to know the species and ability (HA or not) that you will be getting in order to show the correct results.

![](https://i.imgur.com/zQJ9W6i.png)

### As for the delay part, I am gonna activate the honey at frame 536760 so let's see what we get:

![](https://i.imgur.com/Wsv8e06.png)

Nice! I got what I was expecting. The first (the far right one) Starly's stats, match the tool's results for that frame so I am not changing the delay. This is not always the case though so you need to calibrate regardless. Also Pcalc for XY, will only show the stats of the first Pokemon in the horde so keep that in mind when searching for the IVs in the tool to find what you got. (Check the first of the 5 rows for a given frame).

# Finalizing the setup - Hitting the target frame

We saw earlier in the main window that I got 15 identical frames that had the desired IVs and shininess. But which of these should I aim for?

Well, we need to manipulate the TinyMT again to get the desired slot, sync and hidden ability and depending on that, we will know what to aim for.

If you don't care about HA, you can aim for any of these but in my case, I want it so I am looking for the appropriate index.

I found it and set is as current status again. The tool can finally track down the target frame (559094/559095/559096).

Tip: If you want to increase your chances of hitting the correct delay, open all 3 Pcalc Menus (Frame info, Pokemon info and Control mapping at the lower screen.
Works fine for ORAS, kinda unstable for XY but still helpful for me.

By the way the gender doesn't change due to HA but this isn't always the case.

Using the method described above, I can finally land at index 61 and wait until I reach my target frame. Here we go.

![](https://i.imgur.com/XAVVS0V.png)

![](https://i.imgur.com/TdpHR8L.png)

As said before, Pcalc shows the info of the first Pokemon only but since I got the shiny, I can confrim it was a success. I also check the Pokemon's info in my party when I catch it.


# ✨[Bonus](https://www.youtube.com/watch?v=Fp7ajerqOeg)✨


