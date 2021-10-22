# **Normal Wild RNG Generation 6 (Outdated)**

### Latest Guide Update: 27 February 2021

### [Original Page](https://github.com/Bambo-Rambo/RNG-Guides/wiki/Normal-Wild-RNG--Generation-6)

# **What you will need:**

### **Tools**

* [3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases/tag/1.0.5)

* [Pcalc for 3DS](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) or [CitraRNG for Citra Emulator](https://github.com/Admiral-Fish/CitraRNG/releases/tag/v3.1.0)

### **In game**

* Repels and Max Repels (It is recommended to have both)

* Shiny Charm (Recommended if going for shinies)

* Synchronize in the first slot if you want a specific nature or Illuminate if you don’t care about nature

*  Memories do **NOT** affect Normal Wild RNG so no need to worry about them

* It is recommended to be very familiar with Friend Safari RNG

* This guide thinks you have already understood what TinyMT is and why it matters

As you already know, in generation 6, honey and sweet scent are useless in about 90% of the places because they trigger hordes. So unless you want/can use Poke Radar or Dexanv, the only way to activate an encounter for a single Pokemon, is to take a step/turn at the right time. This is especially useful in OR/AS on 3DS since Dexnav suffers unstable delays that cannot be 100% predicted yet. Understanding this guide, will make Poke Radar RNG abuse quite easier.

We are going to see how to trigger an encounter with a single step/turn at the desired frame. Also since Normal Wild's behavior can vary depending on the location, we are gonna try to cover all possible variants and suggest some useful tips for each case.

# **Getting Started**

First choose ‘’Normal Wild‘’ category in the 3DS RNG Tool and use the reseed method to find a frame that satisfies your requirements about IVs and shinyness, the rest (species, nature etc) will be manipulated later. When you find it, right click on it and **Set it as Target Frame**. If you are aiming for a shiny and have the shiny charm, you have 3 possible identical frames to aim for so the even/odd frame thing won't be an issue. I am going to RNG a super size Pumpkaboo [(slot 12)](https://sites.google.com/site/pokemonslots/gen-vi/x) at Route 16. 

![](https://i.imgur.com/eGELNUh.png)

If you are planning on synchronizing the nature later, check the ‘’Assume Synced‘’ button to see if syncing will affect the gender. Ιn my case it actually does so my final target will look like this:

![](https://i.imgur.com/WMv2AEH.png)

# **Setting up the tool**

Open the Tiny Timeline Tool and set the Rate to 13 if you are in grass and to 7 everywhere else (caves, route 17 etc). If your lead's ability is Illuminate, the Rate is 26 for grass and 14 for caves. I am using a synchronizer and my area is grassy so 13 is the number I should set the Rate to.


**Very Important: The following steps will only work if you are trying normal wild RNG in the following places:**

**X/Y: Half of the grassy areas including Route 16, Friend Safari, Route 17 (snow).**

For caves and the rest of the Routes, there are minor differences to the setup that we 're gonna see [later in the guide.](https://github.com/Bambo-Rambo/RNG-Guides/wiki/Normal-Wild-RNG--Generation-6#different-cases)

**OR/AS: Everywhere**

Check the ‘’Consider delay’’ button and click ‘’Calibrate’’. If the tool is connected to your console, the NTR Helper will calibrate the TinyMT for you, otherwise you ‘re gonna have to do it manually every time (not recommended).

This is how your screen should look like:

![](https://i.imgur.com/nN9QQkn.png)

According to the tool, with my current setup at frame '435510', I will get **no** encounter but even if I did, I would get a lvl 36 Foongus and the nature wouldn't sync. Definitely not what I was looking for so I need to find a yellow TinyMT index, which gives me slot 12 and syncs the nature. After scrolling **up** a bit, I found the following TinyMT index: 

![](https://i.imgur.com/z1AzLV7.png)

Enct? is 4 (<13 which is the encounter rate so it becomes yellow and will actually trigger the encounter), Sync? is 'O' which means nature will sync and slot is 12 which is the super size Pumpkaboo I aim for. That's the perfect index for me but it appears between frames '323550' and '323710' which is way before my target (435510) so now I need to match my main Target Frame with this index.

# **Manipulating the Timeline - Method 1 - Slow down the TinyMT**

If you already know how to do this, you can skip to [here](https://github.com/Bambo-Rambo/RNG-Guides/wiki/Normal-Wild-RNG---Generation-6#advancing-to-the-target-frame-hitting-our-target-pokemon)

(Before doing anything, make sure you have got rid of the cooldown that exists after each battle. Take a few steps, 5 for grass and more for caves. In any case, I waste a whole repel for this purpose).

Since my desired index appears before my target, I need to stop the TinyMT from advancing, while the main frame still advances so it can catch up. Entering the bag, advances the TinyMT by 1 index and then freezes it, but exiting the bag also advances it again by a specific (although not fixed) number which is affected depending on your location. At route 16, I found out that it advances by 27 indexes approximately. 27 indexes means around **~1898 main frames**. We are taking notes of these so we can find out how many frames we need to stay inside the bag. 

At this point we can calculate this number. My target frame is '435510' and the desired index appears between '323550' and '323710' so I am gonna subtract ~323570 (random choice which belongs to this range) from 435510 and then add ~1898 which will result in 113838. That's the number of frames I will stay inside the bag. (If you are on Citra, make a save state inside the bag around 2000 frames before exiting).

So after staying inside the bag for that long, I exit and then click ‘’Calibrate’’ again and that's the result I get:

![](https://i.imgur.com/SQNBro8.png)

Pretty close to my target index so that was a decent try. Let's try again. According to the tool, if I had stayed inside the bag for around ~550 frames more, I would land to my target index. (On Citra you can reload the save state you made for this very purpose). 1898 + 550 = 2448 so I am gonna enter the bag again and exit after 2448 frames. Let's give it a try.

![](https://i.imgur.com/X0Rws0t.png)

Success! Frame 435510 matches to the desired index so we are done with the TinyMT part and all we need to do is advance to our frame.

# **Manipulating the Timeline - Method 2 - Speed up the TinyMT**

Instead of searching in the previous indexes for finding the desired one, you can also scroll down and search in the next ones. My target frame is 435510 but I temporarily set this number to 600000 in order to get results. After scrolling **down** a bit, I found the following index which triggers the encounter, syncs the nature and also gives me slot 12. 

![](https://i.imgur.com/Zfw94l9.png)

Should I aim for it? No, because as you can see It's only hittable for 20 (6+14) frames, and placing my target frame between this range will be super difficult and time consuming. Very possible and easy on Citra with save states but still not recommended so I just keep scrolling down. After a few minutes, I still didn't find an index with the desired specs so I understand that in any case I will need to advance the TinyMT a lot and search again. Here are a few way to advance faster:

* Use a Max Repel and run around the grass. Each step advances the TinyMT by 2-4 indexes (NOT including the advances from NPCs or your character's blinking).

* Fly to Route 16 (if you are not there already) and block one of the roller skater's way. This will cause the TinyMT to advance by 1 for every 2 main frames (once again NOT including the advances from other NPCs or your character's blinking).

![](https://i.imgur.com/8iqMQVT.png) 
![](https://i.imgur.com/2AFV1oW.png) 
![](https://i.imgur.com/3meLKsl.png)
![](https://i.imgur.com/0hnARzR.png)

* Use the Pokémon-Amie function which also advances the TinyMT by 1 for every 2 main frames if set up correctly (once again NOT including the advances from other NPCs or your character's blinking).

![](https://i.imgur.com/utgsxSo.png)
![](https://i.imgur.com/8bf6IUc.png)
![](https://i.imgur.com/NwbzC2s.png)
![](https://i.imgur.com/vNtgOEe.png)

* If you can find it, rain also advances the TinyMT by x for every 2 main frames. X varies depending on the location but you can easily calculate it.

* If needed to advance the TinyMT by a specific number slowly, open the Pokedex and start checking different Pokemon's data. Each check advances the TinyMT by 1. Don't forget the number it advances when you exit the Pokedex.

After combining these ways together and returning to my spot again, I pressed ‘’Calibrate‘’, searched a bit more and I found the following index:

![](https://i.imgur.com/vQKkxjf.png)

Not yet done but we are getting there, I am gonna use 2 Max repels and run around the grass. 

![](https://i.imgur.com/zAEMtqC.png)

Oops, that was a bit too much. With my current setup, my main frame (435510) overpasses the desired TiynMT and I need to do the opposite now. So I will return to the [previous method](https://github.com/Bambo-Rambo/RNG-Guides/wiki/Normal-Wild-RNG---Generation-6#manipulating-the-timeline---method-1---slow-down-the-tinymt) to slow down the TinyMT advances.

# **Advancing to the target frame, triggering the encounter**

The difficult part is done but we still need to mind a few things:

* In most places on X/Y, after exiting the bag, if you close the X menu, you get a single TinyMT advancement which can make you miss your target index unless you get rid of it. For this purpose, each time you exit the bag, I suggest pressing the **X** button 2 times to quickly close and reopen the menu in order to 'waste' this advancement, then calibrate.

* The NPC influence in gen 6 is intense and advances the TinyMT, so you need to avoid it by staying inside the menu as much as possible and pretty much force it to become consistent (in case you cannot counter it at all).

Here is my method on how to avoid these issues and hit the correct frame/index no matter what:

When you get close, press **start** and **select** to freeze the game and keep tapping **select** until you are 10 frames before your target, mine is 435510 so I freeze at 435500 **(the X menu is still open)**. Hold the **X** button and tap **select** 8-10 times to advance 8-10 frames (number won't make any difference) while slowly closing the menu. (You get control of your character 10 frames after closing the menu so the purpose here, is to immediately rotate when being able to). Your screen should look like this in that order:

![](https://i.imgur.com/U73dy5O.png)
![](https://i.imgur.com/XfDmJrm.png)
![](https://i.imgur.com/6j4XtG0.png)
![](https://i.imgur.com/dyMtcmi.png)
![](https://i.imgur.com/DA8woAf.png)
![](https://i.imgur.com/GU98zDQ.png)


At this point, simply hold **D-pad** in a different direction than the one your character is looking at and tap **A** to make a turn. If you want to trigger the encounter by taking a step instead of turn, change the delay to 14.

![](https://i.imgur.com/pUbLWRe.png)
![](https://i.imgur.com/An78lh9.png)

# Different cases

As mentioned above, this is not the correct setup for places like caves (X/Y only) and some routes (especially the noisy ones - X/Y only).

In these locations, you actually hit the next TinyMT index than the one you make a turn in. To see every available TinyMT index, **the ‘’Consider delay’’ button must be UNCHECKED.** For example, making a turn at index 38 (397101-397315) will give me the specs of index 39, so the encounter will be successful and I will get a slot 11 Pokemon with the nature synced:

![](https://i.imgur.com/qWNzHLJ.png)

![](https://i.imgur.com/PGKnjqD.png)

# Possible Issues

* You didn't get an encounter at all

Failed attempts may occur due to bad setup. Make sure that you follow the exact method I described above when closing the menu. 

Never forget the necessary steps to get rid of the cooldown after each battle. 5 for grass and more for caves. If you keep getting random unwanted encounters during this process, don't hesitate to consume a whole repel before setting up. 

Remember that caves work differently. Also, triggering a fresh encounter 2-3 steps after the last battle sometimes, means nothing. You still need to take a lot more. 

If you are trying to RNG in places like route 17, it takes some more frames to trigger the encounter so don't forget to get rid of that 1 advance we talked about in after exiting the bag.

Some very noisy places, require a different approach as well. To give you an idea, take a look at the following picture showing how Route 11 works. 

The best way to practice is by far abusing the **auto calibration** function. Ignore the delay part completely, auto calibrate and when you reach a yellow index, go for it and see what you get. Do that multiple times to become familiar. During this whole process, you will be using the **D-Pad** and **NOT** the circle pad, your rollers or your bicycle.

![](https://i.imgur.com/EYM5xK2.png)

Making a turn at index **179**, actually **triggers** the encounter you were supposed to get at index **181**, does **not** sync the nature and the encounter slot is going to be **10 due to index 182** (a lvl 21 Nidorina in this case). Pretty confusing but 100% predictable. Obviously you have to ignore the ‘’Consider delay‘’ box like we do in caves.

* You got an encounter with wrong characteristics

See above

* You sometimes hit ±1,2 frames far from your target but can't predict when

When you reach your target frame do NOT press **select** again. Doing so, apparently does not change anything at first but in fact it does. If you are at frame 500 and tap select once, you will remain at 500 but this doesn't mean that both states are the same. It's the odd/even thing that affects here. Speaking of which, if you don't have the Shiny Charm, or you aim for a non shiny frame, you have to deal with odd/even frames as well. Saving can switch between odd/even but it's not super useful here since messing with the TinyMT is very likely to cause a switch again. Pcalc shows your current state (odd/even) but CitraRNG does not.

