# SOS RNG

While a cool way of obtaining high IV shinies in the wild, including fully evolved underleveled ones, SOS RNG still remains one of the least famous types of RNG
since almost everything is possible with eggs nowdays.

The unstable delay (due to battle RNG), the time taken to build a decent chain as well as a few more inconsistencies, didn't help the situation either.

However, it's still my favourite gen 7 RNG type so I will try to explain my method and provide as much info as possible in this guide 
to make it consistent 95% of the time.

Please keep in mind that this is only my own approach and I will be using Citra Emulator for 2 reasons:
* It can run at full speed making the chain build process way faster.
* SOS ram reading isn't exactly stable. I made some changes in CitraRNG but Pcalc isn't gonna be updated. 
You can wait for a [Pokereader](https://github.com/zaksabeast/PokeReader) update or use Pcalc regardless but it will require some manual input.

The method itself is not actually difficult but it requires a careful and detailed setup, which varies depending on your target.

Having shiny hunted using SOS encounters in the past and/or having understood the [guide](https://www.pokemonrng.com/retail-usum-sos) in Pokemonrng.com, 
will make this guide easier to understand, but neither are necessary.
### Tools
* [Citra Emulator](https://github.com/citra-emu) (Either a Canary or Nightly build)
* [3DS RNG Tool](https://ci.appveyor.com/project/Bambo-Rambo/3dsrngtool/build/artifacts) (my fork with various enhancements and bug fixes)
* [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) (either the original script or [my fork](https://github.com/Bambo-Rambo/CitraRNG) which helps dealing with crashes easier)
* [3DS Time Finder](https://github.com/Admiral-Fish/3DSTimeFinder) (optional for searching high IV spreads)
* [PKHex](https://github.com/kwsch/PKHeX/releases) (for setting up your team)

### Introduction
If you have understood gen 7 egg RNG (without Masuda method or Shiny Charm) in the past, you already know that we keep accepting/rejecting eggs to advance egg indexes, 
and when reach our target **index** (which guarantees IVs, HA, gender etc), we wait in front of the Pokémon Nursery lady until reach our target **frame** to make the egg shiny.

Similarly to this, in SOS RNG we keep defeating allies to advance SOS indexes and when reach our target **index** (which guarantees species, HA etc), 
we wait before the ally appears until reach our target **frame** and make it shiny.

In other words, both egg and SOS RNG, use 2 RNG states instead of 1 which need to be manipulated separately for succeeding with the final target.

### Setting up the team

Use PKHex to inject the following items in your bag if you don't have them already:

* Honey
* Adrenaline orb
* X accuracy
* Leppa Berry
* Cheri Berry
* Roto Boost
* Roto PP restore

As for the steps you need to follow, the general idea of this method is:
* Use the Harvest/Leppa berry combo to prevent the caller from struggling to death
* Minimize the caller's accuracy and maximize your own evasiveness to increase the chance of stabilizing the battle delay
* Build a decent chain to increase the shiny success probability
* Use the paralyze/heal method to advance indexes 1 by 1 and reach your target consistently

The team I use myself can be found [here](https://pastebin.com/vzHEA4Zm).
I will explain more details later.

Copy the info from the above link and use PKHex to inject it in your save (Tools -> Showdown -> Import set from clipboard).

Mew is gonna be the synchronizer but there is a bug with SOS battles that uses the nature of your 1st party Pokemon instead, 
so you need to change Trevenant's (your leader) nature to whatever you aim for.

This team is supposed to have legal movesets but you can always modify it the way you want.

Keep in mind that, unlike what you may have read, using super effective moves against the allies, **does NOT** affect anything.

### Getting Started

First of all, you obviously need to encounter the wild Pokemon which calls the desired ally.

If don't know how to RNG wild encounters, you can use this [guide](https://www.pokemonrng.com/retail-usum-wild) as reference.

* [Gen 7 Wild slots](https://sites.google.com/site/pokemonslots/gen-vii)

After understanding how to wild RNG, and when you have calibrated delay, correction and made sure you are about to encounter the correct Pokemon, 
highlight the Honey inside the bag and **create a save state just before using it**
because you may need to try different SOS seeds until you find what you are looking for by restarting the battle over and over again, 
and having the save state ready will speed up this process.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS1.png)

The annoying part is to actually set everything up and find a SOS index that satisfies you.

Then you will be able to start building your chain and hit your target index + target frame, 
a process which is quite easy now as 3DS RNG Tool will do most of the job for you.

When the encounter starts, go to the SOS tab in CitraRNG, press *Update* to read the SOS seed, then *Pause* and **do nothing else yet**.

While leading with Trevenant, use Trick to pass the Leppa Berry to the enemy and then Skill Swap to give it "Harvest".

You have now advanced the SOS state a bit (most likely by 2 indexes unless the enemy has called for help already).

Press *Update* again and if the values of *Current Seed* and *Index* are updated normally, 
skip to the next [step](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/SOSRNG.md#checking-the-possible-indexes).

If you get an error message **"Exiting an infinite loop. Retry the battle and start updating before taking any actions."**,
press *Disconnect* in CitraRNG and then *Connect* again.

Manually edit the Initial Seed value (in the SOS tab) a bit (increase/decrease by ±1/2) and press *Update* again.

If you get the same error, repeat the process with a different edit (if you tried +1 earlier, try +2 this time etc) until you get no error.

**(Sometimes the script doesn't read the SOS seed correctly so it's impossible for it to calculate the current index thus causing the error,
something also happening with Pcalc sometimes.)**

In my case, you can see that it reads **FABB1D05** at first so I get the error,
but when I changed to **FABB1D04** (-1) and pressed *Update* again, it worked as intended.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS2.png)

This process is a bit tedious but necessary if you want to "save" your seed instead of restarting the battle.

It's also useful if you want to make a save state in the middle of the battle and reload it (implies knowing and manually putting the SOS seed of course).

### Checking the possible indexes

When you have confirmed your SOS seed, it's actually time to check if there are any indexes that meet your expectations.

In 3DS RNG Tool, go to "Tools" -> "Misc. RNG Tool" -> RNG -> G7 SFMT (32bit) -> SOS and set up the tool.

Set the "Length" to anything higher than 30 and the "Call rate" according to [this link](https://pastebin.com/W59vsi0H).

The "IVs" dropdown menu refers to the already perfect IVs that can occur from the main RNG.
This practically means that if your target (shiny) frame, has at least 1 perfect IV **by default** before the SOS bonus, 
it needs to be checked in the menu so the tool can calculate accurate results.

In my case, I used 3DS Time Finder to find a frame that already has 5 perfect IVs (31/31/31/x/31/31) so the tool needs to look like this:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS3.png)

In the "SOS2" tab, set the "Encounter Slot" according to [this link](https://gist.github.com/SciresM/a539739085e24af55dffdf443cb70eb2) for Ultra Sun
or [this link](https://gist.github.com/SciresM/deecdcf5fc49fc8191a29d111643c6b6) for Ultra Moon, always depending on what you are looking for.

The rest of the filters should be self explanatory.
**Don't check the "Success Only" box yet.**

If you don't care about the exact level of your target, leave the value to 0.

I aim for a lvl 9 shiny HA Salamence with sync nature so according to the above links, 
I set the Call Rate to 9 (Bagon), while slot is 1 (1%) and Level is 9 obviously.

Press *Calculate* and if you get no results, reload the save state you created earlier just before using the honey and 
repeat the above steps from beginning (find the actual SOS seed etc).

**Note that when a new encounter starts, you need to manually clear the Initial seed value in CitraRNG by pressing the Backspace button in your keyboard.
The script will only read from ram when there is no seed already, otherwise it will use the existing one.**

If the tool finds something, the final step is to check if the index can be hit somehow.

Right click on it and press *Find Path for index*.

If you get a message **"No path found"**, try a different one.

After a few attempts and trying different seeds, I found that index 307 at seed **46A28F62** is reachable from index 305.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS4.png)

Moreover, according to the tool, I need to use Thunder wave when get close to index 305, 
then I will use Trick to give the enemy my Cheri berry to heal it, it will call for help which will be ignored, 
and I am gonna land at 307 in which case, all I will have to do is wait until reach my shiny frame.

### Battle setup

Enough talking, time to set everything up then start building the chain.

I have already used Trick + Skill Swap to give the enemy Bagon the Leppa Berry + Harvest and prevent it from struggling to death.

I am gonna switch to Smeargle and spam Minimize and then Flash to maximize the chance of the enemy missing its moves.

Then I am gonna use Substitute and Baton Pass to switch to the second Smeargle.

I will use False Swipe to make Bagon's health red (max chance of calling for help) and finally Baton Pass to my synchronizer (Mew).

The stat changes have been preserved and Mew is behind substitute which increases the chance of having stable delay in the last turn before my shiny Salamence appears.

Using an Adrenaline orb is necessary so the enemy will keeping calling for help constantly.

If you will be using Thunder wave instead of Glare, 
use X accuracy because Thunder wave has 90% accuracy in gen 7 and you don't want to miss at the most crucial moment.

Also I recommend using a few Roto Boosts during the battle to prevent the enemy from breaking the substitute too early 
(especially if you are dealing with high level enemies).

### Delay calculation

Since I know that I am gonna advance to the last turn (at index 307) by using another Adrenaline orb (nothing will happen just for wasting the turn), 
I will create the same conditions in an earlier index and make a test to find the exact delay value 
(hopefully Bagon will miss both during the calibration as well as during the final turn).

At index 152, its last call (from 150) failed so according to 3DS RNG Tool, 
a new Bagon will surely appear in the next turn whose stats I am gonna check to find my delay.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS5.png)

(Note that when Adv. = 1 the Pokemon will not call for help at all, 
when Adv. = 2 the Pokemon will call for help but will get no response 
and when Adv. > 2 the Pokemon will call for help and a new ally will appear).

In the main window, check the *SOS call* box and put your SOS initial Seed, current index and chain length.
If you get no results at all, make sure that the correct ally is selected.

Uncheck the *Consider delay* box and don't forget to change the NPC value to 0 since they don't affect anything during the battle.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS6.png)

Notice how frames 20349-20351 have some weird marks.

These practically show that state 20350 is gonna remain the same for 5 frames and state 20351 for 30 frames.

This can be abused for good purpose if those marks exist inside your shiny target frames to increase the shiny range but otherwise they should be avoided, 
especially when calibrating delay so I am gonna calibrate at frame 20360.

### Final Steps - Hitting the taget ally

After knocking out some Bagons, I reached index 298.

This is very close to 305 so I should proceed with final steps.

Using Thunder wave here, will prevent Bagon completely from calling new allies, 
while the SOS state will keep advancing by 1 every turn.

Before anything though, I am gonna use Skill Swap to send away the Harvest ability I gave it earlier and prevent it from restoring the berry 
which would practically have 50% chance of messing with the delay.

By the way, if there are 2 Pokemon on the field, make sure to use Thunder wave before knocking out the second one, otherwise the first, 
may call for help, suceed and overtake your target index.

After wasting 7 more battle turns I reached index 305 so now I have to use "Trick" and give the enemy Bagon my Cheri berry to heal its paralyze status.

I expect it to call for help which will be ignored, and jump to index 307.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS7.png)

There we go!

I landed at my target index (307) and since there is no ally on the field, 
all I have to do now is wait until reach my target (shiny) frame and then waste the turn by using another Adrenaline orb.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS8.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS9.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS10.png)


