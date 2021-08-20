# Gen 6 TID/SID RNG on Citra

### Latest Guide Update: 20 August 2021

### [Original Page](https://github.com/Bambo-Rambo/RNG-Guides/wiki/TID-SID-to-time-RNG-Generation-6)

# What you will need:

# Tools

[3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases/tag/1.0.5) by wwwwwwzx

[CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases/tag/v3.1.0) by Admiral-Fish

[Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder) by me


The tool I provide for this guide is meant to work for Citra. You can attempt this on console but expect to spend a lot of time calibrating and manipulating the TinyMT due to the millisecond accuracy required when booting the game.

# Finding the appropriate date

(The TID/SID generation in gen 6 games only uses the TinyMT RNG so the main initial seed for this purpose is not needed, we are not going to use it in any way).
Delete the existing save file if you haven't already by pressing **Up + B + X simultaneously** in the loading screen then **close Citra**. Load it again, go to Emulation -> Configure -> System -> Clock, choose ''Fixed Time'' -> Startup time. You can set the year to whatever you like, but everything else has to be set to its initial value except the hours which should be set to 13. (The date 20xx-01-01 00:00:00 is not consistent because different NAND/Timezone combinations may affect the actual RTC)

I want my trainer card to show 2021 or later so I set the date as following:

![](https://i.imgur.com/1zFzQZA.png)

Load the game and pause in the **language select screen**. Open CitraRNG, connect it to Citra and get the initial TinyMT state consisting of 4 hex numbers:

![](https://i.imgur.com/MDvhpIS.png)

In Tiny Finder, use the "**Date Searcher**" Tab and fill in the boxes with the appropriate info. 

In the "Calibration" box, paste the initial state.

Select the game version, the month to search results in, the max number of advances you are willing to waste, the desired TID and SID (max 65535 for both) and the maximum number of results you want the tool to find. For ID RNG, it's suggested to be 1-2 max, because the list won't be updated until all results have been found.

### **Important**

The "month" combo box in the "Settings" box, is used for the results, NOT for the calibration. You are using the month 1 (January) for calibration no matter what and then you pick the desired month as a starting point. If the tool doesn't find something in the month you picked, it's gonna keep searching in later months/years until it finds something. 

Be very careful. Double check the year and the TinyMT state. Putting any of these wrong, will result in the tool searching forever and/or show wrong results.

![](https://i.imgur.com/wB09iaF.png)

Press "Search" or "Calibrate and search" (if the tools hasn't calibrated already) and let it do the research for you - it will freeze while searching, don't worry. It shouldn't take long (considering everything was put right). When you get a result that satisfies you, copy paste the date from the cell directly to Citra RTC (the date format is identical for that purpose) and if everything was done right, you will get the same TinyMT state in CitraRNG:

![](https://i.imgur.com/BjWBpkV.png)
![](https://i.imgur.com/Sxvnu8Y.png)
![](https://i.imgur.com/KxethvD.png)

# Hit the target frame/index - Get the desired TID/SID (XY)

If you are doing this in X Y, you still have work to do. Choose your character's gender and name and advance to the following screen:

![](https://i.imgur.com/vlAu9Qd.png)
![](https://i.imgur.com/PNQafHs.png)

Update CitraRNG to show you the new TinyMT state, open the Tiny Timeline Tool and set it as shown in the above picture. Once you put your current TinyMT state, **you are not going to change it again**. Start advancing frame by frame and when the TinyMT state changes, put the (frame - 2) in the first 'Main RNG Frame' box.

![](https://i.imgur.com/NwA9iJe.png)
![](https://i.imgur.com/X347Ag3.png)

As you can see, frame 5805 was the last one before the TinyMT state advances so I put (5805 - 1) = 5804 in the box (remember the odd/even issue).

I need to follow the same process 3 more times **without changing the 4 hex numbers** in the 'Calibration' column. After some time and patience, I click 'Create' and the tool shows my current timeline. It can predict the main frames in which the TinyMT state is going to change. For example in the following image, the TinyMT 'index 10' will last for 52 main frames (6572-6622).

![](https://i.imgur.com/zA3oKiw.png)

Time to find the frame range in which we are going to Hold 'A' so we can hit our target TID/SID. Return to the Main Window in 3DS RNG Tool and paste the TinyMT index you have in the Tiny Timeline Tool. Click 'Calculate' and find your target index.

![](https://i.imgur.com/id7rJwo.png)
![](https://i.imgur.com/pBd0WGp.png)

I aim for index 108 so I finally return to the Tiny Timeline Tool, check the **'Consider Delay'** box, change the 'Target Frame' to a number of my choice (say 20000 - doesn't matter/mainly to expand the timeline) and click 'Create'. I am looking for the number 108 **in the 'Hit' column**. 

There we go. Holding 'A' between frames 15014-15094 (at index 99) will send me to index 108 (because of the delay until the TID/SID are generated) which is my target index. Let's see what we can do:

![](https://i.imgur.com/U5X65wW.png)
![](https://i.imgur.com/09f1dGR.png)

When Fletchling appears on the screen, the TinyMT freezes and doesn't change until the player wakes up. This is where the TID/SID are generated so you can confirm it a bit earlier without waiting to check your Trainer Card.

If you find this complicated, you can always go with Citra save states. When holding 'A' in the previous screen to finalize the process, we saw that the TinyMT advances about 6-9 indexes so we can use it as the base delay and abuse the save states until we hit our target.

# Hit the target frame/index - Get the desired TID/SID (ORAS)

Things are ridiculously easier if you do this in ORAS games. The TinyMT advances by 10 until you choose the gender and then each time you enter in the name selection screen it advances just by 1 in a way similar to gen 5 and gen 7 games. Just keep choosing 'NO' whenever the professor asks you to confirm your name. When typing your name, you must be in your target TinyMT index:

![](https://i.imgur.com/NOqX7mQ.png)
![](https://i.imgur.com/yvoPQ8Y.png)
