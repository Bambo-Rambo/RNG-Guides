# Normal Wild / Friend Safari RNG - Alternative method

When thinking about TinyMT RNG in gen 6 games, the first thing that comes to mind is the need to manage 2 RNG states simultaneously (MT and TinyMT). 

Normal Wild, Friend Safari, Fishing, Rock Smash and even stationary sync, require TinyMT manipulation in order fit the main frame into the target index.

However, there are some methods like hordes and PokeRadar which are considered easier because this synchronization is not exactly required.

For both methods, we deal with the TinyMT first (by reaching our target index) and wait until we reach our target frame, then interact.

* Could we possibly do the same for harder methods like Friend Safari and Normal Wild RNG?
* Could we land on our target index and wait until we reach our target (shiny) frame and avoid the tedious proccess of matching the 2 states together?
* Could we avoid using the Tiny Timeline Tool in 3DS RNG Tool AT ALL?

The answer to these questions is obviously yes otherwise this guide wouldn't exist. 

It would have to be a quiet place with no active NPCs though which of course is a restriction, but such places include: Friend Safari, caves as well as some routes.

These are common areas with large groups of available Pokemon, especially Friend Safari so we can save a lot of time and effort where appliable.

### Getting Started

Connect your console to 3DS RNG Tool using the NTR Helper and reseed until you find a nice spread.

Fly to where the target Pokemon is, and stand on a grass patch.

Open TinyFinder and track down the desired index.
It can be any and you don't have to worry about Blink (+2) advances, because we will hit it no matter what.

![](https://i.imgur.com/pHssMu5.png)

Depending on how far it is, you may use various methods of advancing fast. We will see them soon.

When you get close, like 50 indexes away, enter the bag.

In XY, the TinyMT advances that you get when closing the bag using the 'X' button (not 'B'), are 27 + 1 extra advancement when the lower screen menus (PSS etc) are reloaded.

In ORAS, this number is 15 + 1.

Since the numbers are predictable and consistent, we can abuse them to land on our target index from the bag.

This means that if I am 28 indexes away from my target inside the bag in XY, closing the bag will get me there.

And since the TinyMT state freezes inside the bag, I can wait until I get ~100 frames before my target and then press 'X' to exit the bag and that's pretty much it.

Let's take an example:

I want to catch a lvl 36 shiny Klefki at Route 15 and I aim for frame 15915 in 3DS RNG Tool so my setup should look like this:

![](https://i.imgur.com/37uKB8X.png)

I won't be using the Tiny Timeline Tool at all and no calibrations will be made.

To advance fast, I will use the rain at Laverre City.

(If you can't find the rain anywhere, you can either use the Pokemon Amie function in the lower screen or fly to Route 16, 
and also stand in front of one of those roller skaters.
Either method advances by 0,5 index every 1 frame, so combining both, will advance by 1 index every 1 frame)

![](https://i.imgur.com/Hrp9Tyy.png)

After a few seconds, I am ~300 indexes away so it's time to return to Route 15.

Here are some ways to advance inside the bag slowly:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 (In fact what advances here, is checking the summary screen of the Pokemon). 
Don’t actually teach the move otherwise it will advance more.
* Giving your Pokemon a held item, usually advances by 3. (Rarely by 4, not exactly sure when).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 4 Pokemon in your party, using the Exp Share, will advance 3 * 4 = 12 indexes etc

By spamming the Exp share on/off inside the bag, and giving my party Pokemon some held items, 
I eventualy reached 28 indexes before my target and all I need to do now is exit the bag at frame (15915 - 100) = 15815.

A few more Select taps to reach 15915, an 'A' + "Right" press to rotate the character and here we go: 

![](https://i.imgur.com/1P9JTHR.png)
![](https://i.imgur.com/Pode3HO.png)

![](https://i.imgur.com/67mQmcc.png)
