# Horde Encounter RNG Abuse Guide

There are 3 ways of triggering a horde in gen 6 games:

* Using Sweet Scent - Guaranteed horde
 
* [Using Honey - Guaranteed horde](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/HordeRNG.md#honey-method)
 
* [Moving in the grass - 5% chance for horde](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/HordeRNG.md#moving-method)

In this guide, we are gonna explain 2 of the 3 ways, Honey and Moving.
While Sweet Scent works in a way simillar to Honey, 
its delay is more unstable and no public tools currently support it due to different setup.
That said, from now on, we are gonna pretend that Sweet Scent doesn't exist at all.

# Tools

* [3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases)
* [Tiny Finder](https://ci.appveyor.com/project/Bambo-Rambo/tinyfinder/build/artifacts)
* [Pcalc](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) for 3ds or [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) for Citra Emulator

# Extra

* Repels
* Shiny Charm (recommended)
* [Normal Wild RNG guide](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md) (required reading for Moving method)
* [Multi shiny seeds](https://pastebin.com/FjGLi6vq)

# Introduction

Like most gen 6 rng types, a complete horde encounter rng requires manipulation of both the MT and TinyMT states.

MT (Mersenne Twister / the initial seed), generates the PID (shininess), the IVs (stats), gender (if not genderless), 
ability (if not HA) and the nature (unless force synced).

TinyMT (Tiny Mersenne Twister), generates the encounter slot (species), the synchronize success, 
the HA possibility, and if doing the Moving method, the successful horde trigger.

For the MT part, we are gonna be using 3DS RNG Tool while for the TinyMT part, Tiny Finder, both reading info from Pcalc.

**To avoid any confusion between the 2 algorithms, I am gonna be using the term "frame" for a MT state and "index" for a TinyMT state.**

As for frames, we can see that 3DS RNG Tool shows the PID and stats of all 5 Pokemon in the horde for each frame.
The first 5 rows represent the resulting horde for frame 0, the next ones for frame 1 etc.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde0.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde1.png)

If you have the shiny charm, you will be getting 15 identical shiny frames with the same traits.
This happens because the charm affects each Pokemon seperately.
Like Normal wild shows 3 identical shiny frames, here we have 15.
We will see later which of these to aim for.
Just keep in mind that each of these shiny frames represent a different horde.

### Honey method - Prons and cons

* (+) Quite easy to find and hit your target TinyMT index (the correct slot, sync, HA etc)
* (+) No chance of failing the horde encounter
* (-) Unstable delays can result in getting the correct species but wrong stats, PID (no shiny) etc

### Moving method - Prons and cons

* (+) Stable delay (+6) - No need to calibrate
* (-) In ORAS, only possible at long grass
* (-) The desired index might be very far away, if you miss it, you won't have a second chance
* (-) Harder to do overall

There is no way to tell which method is actually "better".
Depending on the case, one may be more effective that the other.
I am gonna explain both and you can choose whichever works better for you.

For either of the two methods, I recommend using the NTR helper in the 2 programms with Pcalc to make the whole process easier

Connecting to 3DS RNG Tool will allow you to search for nice spreads faster, 
while Tiny Finder will read your TinyMT state with one button press without having to type it manually every time.

# Honey Method

There is nothing really difficult here. 
After calibrating the delay for the main (MT) rng once, 
we are gonna prepare the TinyMT part to guarantee the correct species, nature sync and ability, 
then wait inside the bag with the Honey highlighted until we reach our target frame.

Make sure that you have already saved the game in the desired route/location beforehand.

### Searching for the desired frame

In 3DS RNG Tool, pick your location and the desired species.
You are gonna need to RNG for the species (TinyMT), but for now we will take is as granted to get accurate results.

Use the [reseed](https://github.com/wwwwwwzx/3DSRNGTool/wiki/NTR-Helper-Usage#note) method until you find a (shiny) spread that satisfies you.

If you care about the gender of the Pokemon, keep in mind that it may be the opposite of the one you see in the tool, 
if you plan on syncing the nature and/or manipulating for the HA.
In that case, check the "Assume Synced" box in the tool, select a random nature from the list and set the value of the "HA" box to anything between 1-5.
The frame(s) with the Hidden Ability will show the correct gender.
Don't set them as target frames yet, we will get back to this later.

### Getting Started - Calculating the Honey delay

Load the game and enter the bag. 
The first try will be random in order to find and adjust the delay for our current locaton.

Inside the bag, highight the Honey and press 'A' once so you will be ready to use it.

In the `Generator` tab of **Tiny Finder**, select the `Horde` method, 
choose your location and carefully put the exact number of Pokemon in your party.

Click "Update" and the tool will read and show the results for your current TinyMT state.

**If you have messed with the preferences, click `Ignore Filters`, you want index #0 to be visible in the results no matter what.**

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde2.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde3.png)

Index 0 in the first row practically says that if I use honey right now, synchronize will **not** work,
and the species will be five Zubats (slot 1) none of which will have the hidden ability.

This step is necessary because, for 3DS RNG Tool to calculate the results (PID, stats etc) accurately, it needs to know the above info (HA, sync).

In my case, according to Index 0 from Tiny Finder, I need to select `Zubat` in `Meteor Falls (2)` location in **3DS RNG Tool**, 
leave the "Assume Synced" box unchecked and the `HA` number set to 0.

In order to find the delay, I freeze the game by pressing Start + Select at frame 50382 (you choose any frame for calibration - this is just a test run), 
I set it as target frame (Right Click -> `Set as Target Frame`) then hold `A` to unfreeze and use the Honey.

(BTW I have noticed that having all 3 Pcalc menus open will result in more stable delays in caves.)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde4.png)

By pressing Start + Left, we can see the wild Pokemon's stats (tap Select + Right after pressing Start + Left to scroll between the rest of the Pokemon in the horde). 

As expected, the TinyMT part is correct. 
5 Zubats, random natures even though I am leading with synchronize and no HA either (Index 0). 

The spread of **"Enemy Pokemon 1"** is `30/18/1/29/1/9` so I am gonna put it in 3DS RNG Tool and press "Calculate" to find how off I was.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde5.png)

Notice that the tool shows 5 simillar frames with the same spread. 

Since I put the spread of **"Enemy Pokemon 1"** though, I know that the actual frame I hit, was 50374 (slot 1).

(Keep in mind that the term "slot" here, implies the position of the Pokemon in the horde. No relation to the encounter slot table at all.)

To calculate the actual delay, just add the number from the "Shift/F" column to the current delay.

174 + (-8) = 174 - 8 = **166**

### Finding the right index, hitting our target

Run away from the battle, and enter the bag again.

In Tiny Finder, choose the desired species (I will go for a horde of 5 Bagons), 
if you want your target to have its Hidden ability choose "Any slot", 
check the `Sync` box if you want to sync the nature and if playing ORAS, 
ignore the flute boxes unless you care about the exact level of the Pokemon.

Press `Update` and the tool will show all indexes that meet your requirements in the selected range (0-50000).
You may target any of them (probably the earliest one).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde6.png)

The earliest Bagon horde, with the HA and nature sync requires 49 advancements.

Here are some ways to advance inside the bag:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 index (In fact what advances here, is checking the summary screen of the Pokemon). Don't actually teach the move, otherwise unwanted advances will occur. Don't stay in the move selection screen for too long, otherwise the Pokemon will blink and unwanted advances will occur.
* Giving your Pokemon a held item, usually advances by 3 indexes (rarely by 4).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 4 Pokemon in your party, using the Exp Share, will advance 3 * 4 = 12 indexes.

I have 5 Pokemon in my party so there will be 5 * 3 = **15** advances per Exp share usage.

Since I need 49, I can use the Exp Share 3 times (3 * 15 = 45), give one of my Pokemon a held item (+3) 
and finally attempt to teach it a new move (+1).
The total is (45 + 3 + 1) = 49 and that's pretty much it.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde7.png)

There we go!

My current TinyMT state matches the one of my target index.

It is now guaranteed that using Honey here, will generate a horde of 5 Jolly (my leader's nature) Bagons where the 2nd one will have its Hidden ability (Sheer Force).

Time to track down our exact target frame(s) so we know exactly when to use the honey, one more "tricky" step and we succeed.

In 3DS RNG Tool, choose "Bagon" (or whatever slot 3 is for your current location), change the HA number to 2 
(or whatever slot the HA is in your case) and adjust the Nature settings.

**Important: Your target index may has the HA even if you don't care about it. 
In this case, you still need to put the exact HA slot number in 3DS RNG Tool so it can calculate the results accurately 
and you will just aim for the frame(s) that don't have it.
Or you can deliberately aim for an index with no HA.**

In the following image, frames 279306-279308 are the ones I should go for since they have the HA in slot 2, 
so I just need to wait until I get there, with the Honey ready for use and all 3 Pcalc menus open.

Notice how the gender for all those shiny frames changes from female to male after the "Assume Synced" box was checked. HA didn't affect this time.

I am expecting the shiny with the HA in the second spot (from right to left) of the horde.
Let's go!

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde8.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde9.png)

# Moving Method

* **This is similar to the Normal Wild method you can find in [this guide](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md) 
which I highly recommend reading first. If you already did, you may proceed.**

* **Having the shiny charm is highly recommended to deal with the odd/even frame issue.**

Until now, we didn't have to worry about triggering a horde encounter since Honey did the job for us.

Now things are going to be tougher, the idea is to trigger the horde by moving (step/turn) the player character at the right index.

To get an idea, let's take a look at the numbers:
* Using Honey: **100%** chance of triggering a horde no matter what
* Taking a step/turn: 13% (or 7% for caves) chance of triggering **any** wild encounter + 5% chance of this encounter being horde 
=> **0,65%** chance in the grass and **0,35%** in caves.

Good news is that we don't need to calibrate the delay, value is always +6.
In fact, when you get used to this method, it's gonna be the recommended one, 
since the Honey method is problematic on the delay part and may screw you up even if you do everything right.

**Remember that if playing ORAS, this is only possible in [Long Grass](https://bulbapedia.bulbagarden.net/wiki/Tall_grass#Long_grass).**

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/HordeThink.png)

### Finding the minimum hittable frame based on our target index

In Tiny Finder, select the `Moving` option and fill in the rest of the fields accordingly.
If you are leading with Illuminate instead of Synchronize, double the ratio value for the current location (typically 14 for caves and 26 everywhere else).

Your party number doesn't matter for this method.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde10.png)

As said, the chance of triggering a wild horde each time we take a step/turn, 
is significantly lower than using honey, so the possible TinyMT results will be way more limited.

This means that a least number of frames will be spent until I reach my TinyMT index.

In other words, the target index affects the minimum frame number I can aim for, 
because I don't want to miss my shiny frame while I am setting up the TinyMT part.

* In XY, the most reliable way to advance the TinyMT state fast, is to spend time in a wild battle at Route 17 (~1 index per frame). 
* In ORAS, fly to the south part of Route 121 where it's raining (~3 indexes per frame).

Use these 2 ways to advance, and when you get close (around 1000 indexes before), return to your location. Image sample for XY (left) and ORAS (right):

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde11.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde12.png)

Index 1120 matches my preferences and is so close that I won't even go to Route 17 for advancing faster
(I was lucky this time but don't expect it to be always like this).

### Setting up 3DS RNG Tool

I am gonna set the minimum frame in 3DS RNG Tool to 10000 to be safe.

I also need to put the info of index 1120 from **Tiny Finder** (nature sync, slot = 3 and HA = 2) in order to get the correct results.

My location will be Frost Cavern and slot 3 is Smoochum (which belongs to the undiscovered egg group by the way, so it will have 3 guaranteed perfect IVs).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde13.png)

### Preperation

If you have read the **[Normal Wild guide](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md)** I recommended eariler, 
you already know that we need to take a few steps before being able to trigger wild encounters by moving. 
(Wasting a whole repel - 100 steps - to avoid random encounters, is recommended especially inside caves). 

When the repel effect ends, **don't use another one** and instead, enter the bag and click "Update" in Tiny Finder.

**Very Important: In the Honey method, we advanced to our exact target index, waited until reach our target frame and then used the honey. 
Now we need to advance until we are `X` indexes before our target index, wait until reach ~100-120 frames before our target frame and then exit the bag, rotate the character and trigger the horde.**

We do this because, when exiting the bag, there will be `X` TinyMT advances that need to be accounted for.
And this process takes about 100-150 frames depending on your location.

The value of `X` will be:
* **15** if playing ORAS
* **27** if playing XY
* **3** inside caves for either game version (My case here)

You can see some exceptions for the value of `X` for XY [here](https://imgur.com/a/pGk0bhM) and for ORAS [here](https://imgur.com/a/B3URhjo). 
These albums also show the recommended spots you should be standing on when doing the RNG.

Once again, here are some ways to advance inside the bag:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 index (In fact what advances here, is checking the summary screen of the Pokemon). Don't actually teach the move, otherwise unwanted advances will occur. Don't stay in the move selection screen for too long, otherwise unwanted advances will occur.
* Giving your Pokemon a held item, usually advances by 3 indexes (rarely by 4).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 6 Pokemon in your party for example, using the Exp Share, will advance 3 * 6 = 18 indexes.

My target index is 225 now, and since the value of `X` for Frost Cavern is 3, 
I need to advance **222 indexes** (225 - 3 = 222).

My party consists of 6 Pokemon which means that every time I use the Exp share, there will be 3 * 6 = **18 advances** 
so I will use it 12 times (12 * 18 = 216) and to reach 222, I will also give a held item to 1 of my Pokemon 2 times (2 * 3 = 6).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde14.png)

**The TinyMT part is done so now I just need to wait until reach ~120 frames before my target then I will press 'B' to exit the bag.**

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde15.png)

In the 'X' menu now, advance until you are **10** frames before your target.

Hold the 'X' button and tap select 8 times to slowly close the menu while advancing frames.

At this point, you should be at your target index and -2 from the target frame (the game is still frozen).

Hold one of the D pad arrows in a direction different than the one your character is looking at, and press 'A' to unpause and rotate.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde16.gif)

