# Horde Encounter RNG Generation 6

### Latest Guide Update: 1 March 2021

### [Original Page](https://github.com/Bambo-Rambo/RNG-Guides/wiki/Horde-Encounter-RNG---Generation-6)

### **Currently searching some stuff. What you read below may be outdated.**

# What you will need:
# Tools
* [3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases/tag/1.0.5)

* [Pcalc for 3DS](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) or [CitraRNG for Citra Emulator](https://github.com/Admiral-Fish/CitraRNG/releases/tag/v3.1.0)

# In game

* Honey (preferably) or Sweet Scent to trigger the horde

* Shiny Charm (Highly recommended if going for shinies)

* A Pokemon with the Synchronize ability in the first slot if you want a specific nature

* Having the White flute in the bag (OR/AS only) is recommended

* Maximizing the memories of all Pokemon in your party is also recommended

* Some experience with RNG manipulation in generation 6

* This guide thinks you have already understood what TinyMT is and why it matters

Being possibly the easiest type of RNG abuse in generation 6 out of the ones that include TinyMT, hordes can be triggered no matter what, by using honey or sweet scent (not recommended) and you can get some nice stuff out of them, including hidden ability shinies in the wild. However, it has its issues namely unstable delay as well as weird TinyMT behavior in some places. In this guide we are gonna see how to manipulate the Horde Encounters and get our desired Pokemon about 90% of the time.

# Getting Started

First choose the ‘’Horde‘’ category in the 3DS RNG Tool and press search. The frames will appear in a different way than usual because the tool shows all 5 Pokemon's stats in a single horde for each main frame. 

![](https://i.imgur.com/ZIBtMwz.png)

Once you get the point, select the place you are gonna RNG to, and use the reseed method to find a frame that satisfies your requirements about IVs and shinyness. The rest (species, nature, HA etc) will be manipulated later. If going for shinies, you will get 15 identical shiny frames for each spread if you have the Shiny Charm or 5 if not. We're gonna see later which of these we will be aiming for. If you are planning on syncing the nature, check the ‘’Assume Synced‘’ button and select the nature of your synchronizer in the tool to get an idea of how your final target will look like. If you are aiming for the Hidden Ability on your target, the gender may be opposite than the one the tool shows you **at first**. In any case, after the setup, the gender will be predictable **before we hit our target**.

![](https://i.imgur.com/ckdXreb.png)

I am going to RNG a shiny Skarmory at Route 113 which is [Slot 3](https://sites.google.com/site/pokemonslots/gen-vi/omega-ruby) and these are going to be its specs, with the addition of Hidden Ability that I am going to RNG for, as well.

# Setting up the tool

(The following setup only applies if you are using **honey** in the **grass** for either X/Y and OR/AS. For caves we are going to explain later what to do).

As mentioned above, both the delay and the TinyMT have their issues in hordes, so we need to test them and see what we get depending on our location. 

In game, activate the White Flute if you have it. I will explain soon why. 

![](https://i.imgur.com/n9CkMxH.png)

I generally suggest doing this test around 50000 frames before your actual target so you can predict the delay better but that's totally up to you. If you are having hard time dealing with the short time range of ~50000 frames, you can test earlier and save more time for the final manipulation.

Open the Tiny Timeline Tool, select the exact number of Pokemon in your party and hit ‘’Calibrate‘’. You will get a bunch of different results so pick one for testing. 

![](https://i.imgur.com/b59hnuA.png)

I will try to hit index 8 which gives me a synced slot 3 (Skarmory) so what I need to do is enter the bag at index 7 (remember that entering the bag advances the TinyMT by 1 and then freezes it until you manually advance it again). Also I am gonna use honey at frame 71000 so let's what we get.

![](https://i.imgur.com/P9jolmt.png)

I got Jolly (synced) Skarmories in the horde and their levels, from right to left, are 6,8,8,8,7 respectively. Considering that the original level of Skarmory in hordes is 9, this means that the White Flute effect is 3,1,1,1,2 so I can say for sure that I hit the correct index. If my predictions were wrong, the White Flute would really help me locate what did I get and plan accordingly for the next time.

Time to check the delay. Let's put the stats of the 5 Pokemon that Pcalc shows, in the tool. Pressing **Start + Left** shows the stats of the first Pokemon in the right and then, pressing **Select + right** scrolls through the stats of the rest Pokemon in the horde.

![](https://i.imgur.com/G99J1IE.png)

After using the honey at frame 71000, we actually hit frame '71016' so we need to increase the delay by 16. The default value in 3DS RNG Tool is 174 so in my case I will increase it to 190.


# Manipulating the TinyMT

As we can understand, the main difference between Horde RNG and other types of RNG abuse in generation 6, is that the TinyMT part in hordes, is being done separately from the main (delay) RNG. This is what makes Hordes significantly easier than Normal Wild RNG for example which requires you to match the target frame inside the target index.

So basically the main idea here is to enter the bag at the right time and then simply wait until we reach our target frame. Let's calibrate again to see what we get. After scrolling down a bit, I found the following index:

![](https://i.imgur.com/LrM6L4l.png)

It will be Skarmories, with synced natures, the levels are going to be 8,6,7,7,8 and the 2nd, is going to have its Hidden Ability. But wait, we said before that entering the bag advances the TinyMT by 1 and then freezes it. So how are we gonna land at index 58 since 57 is not accessible with our current timeline? Well, entering the bag at 56, is gonna throw us to 57 and then all we need to do, is advance the TinyMT by 1 inside the bag. Let's see how:

We are currently at index 57 and we need 1 more advance. The best method I could find for this, is to attempt learning one of our Pokemon a new move then reject it. So I am gonna try learning my Mew the move 'Aerial Ace' and when it asks me to replace an old move, I will press **B** and reject it.

![](https://i.imgur.com/gwHcHGX.png)

(If you are planning on doing this with Sweet Scent, you can advance the TinyMT one by one inside your Party, by attempting to give one of your Pokemon a held item. When the item list opens for you to choose, press **B** to return to your Party and this will advance to the next index).

As you can see, I am now at the desired index and unless I mess up my TinyMT, which I won't, I am gonna get the characteristics shown above. 

# Picking the right frame - Hitting our target

The last thing to do, is hit the frame that makes the HA Skarmory, in the 2nd slot specifically, shiny. So **I set my current TinyMT index as ‘’Current Status‘’** and press ‘’Calculate‘’ in the main tool. It clearly shows me which 3 possible frames should I aim for (in my case 125836-125838) (as mentioned above, the presence of Hidden Ability advances the gender frame by 1 one which can switch the actual gender of your target. Notice how the 3 shiny frames with HA are females while the rest remain unaffected).

![](https://i.imgur.com/Op4tQtT.png)

Ignore the **‘’Species‘’** text in the tool because it gives wrong info most the time. Mind only for the red boxes in the picture.

(To avoid any possible confusion, the term **‘’slot‘’** here refers to which of the 5 pokemon has its HA. Slot 2 means it's the 2nd Skarmory. Not to be confused with the term **‘’Encounter Slots‘’** which refers to the possible wild Pokemon that can appear depending on the location).

After finishing the setup, simply let the frames advance and hold the **A** button when you reach your target. I am gonna use honey at frame '125838' because some times I hit 1-2 frames earlier. There we go:

![](https://i.imgur.com/iOHWDcj.png)
![](https://i.imgur.com/ImzF1oo.png)

# Different cases

Depending on the place (as always) you may face unstable TinyMT indexes as well. For example in some routes the TinyMT advances more when you exit the bag (including exiting due to the usage of honey) and you may actually hit 1-2 indexes **after** your target sometimes so you need to check beforehand. I haven't looked into every place but it's nothing hard to figure out yourself simply by testing. 

Caves have their own behavior in Hordes as well. If you are trying to RNG in an OR/AS cave, you actually hit indexes that are **before** the ones in which you use honey at and this can cause a lot of confusion and error. To set it up ‘’right‘’, set the ‘’**Party**‘’ number to 1 while you actually have 5 Pokemon in your party. As you can see in the following images, my Party consists of 5 Pokemon while the tool thinks I only have 1 and I am about to use honey at index 6.

![](https://i.imgur.com/xq6fprN.png)

![](https://i.imgur.com/OtAyv4s.png)
![](https://i.imgur.com/fqPU7nZ.png)

Different info between the tool and my actual setup, but still the expected result. In Meteor Falls, I got 5 Bagons whose levels are (from right to left) 19,18,17,16,18, the natures synced and the 5th one also has its Hidden Ability. This is **only** correct if using **Honey** since Sweet Scent has different setup. 

You can have different number of Pokemon in your party if you want, but keep in mind that each Pokemon advances the TinyMT by 3 with its existence. So for example, if you have 6 Pokemon you land 3 indexes **after** your current one, if you have 4 Pokemon you land 3 indexes **before** etc. In any case, the value of the ‘’**Party**‘’ box in the tool, should be set to 1.

This setup applies to **OR/AS caves only**.

Bonus: 

![](https://i.imgur.com/07gG6Gi.png)
