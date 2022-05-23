# Gen 6 Main (MT) Seed RNG

The initial (MT) seed generation in gen 6 games is being affected by many things and thus is really flexible.

With the correct steps, we can take advantage of this and force a specific seed inside a specific date of our choice.

This is useful when the user wants the Pokemon's summary screen date to match the actual date of the RNG.

It is also possible to force a specific seed in a specific date + time which is useful for simultaneous manipulation of both the MT and TinyMT seeds.

Keep in mind that, while possible on real 3ds, gen 6 MT seed RNG, is tedious and may not worth your time.

For this guide I am going to explain the method for Citra emulator only.

**If you don't care about the exact date of your Pokemon, you can read the 
[original method](https://pokerng.forumcommunity.net/?t=61239900#entry441604733) instead, written by Real.96.**

### Tools
* [Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder/releases)
* [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases)

### Additional Tools
* [3DS RNG Tool](https://github.com/Real96/3DSRNGTool/releases) (Fork from Real.96, for the above method)
* [Gen6SeedTimeFinder](https://github.com/DevonStudios/Gen6SeedTimeFinder/releases) (for the above method)
* [3DS Time Finder](https://github.com/Admiral-Fish/3DSTimeFinder) (for seed searching. Tiny Finder can be used as well)

# Seed RNG - Specific Date only

Use Tiny Finder or 3DS Time Finder to search for a seed of your choice.

Load Citra and go to -> Emulation -> Configure -> System -> Clock and set it to "Fixed Time".

Then set the date in the "Startup time" option to the actual date you want **and the time to 00:00:00**.  

My target date is May 23 2022 so it should look like this:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed1.png)

Load the game, open CitraRNG and connect with Citra then skip the final cutscene at a frame of your choice **and write it down somewhere**.

The final cutscene screens for XY (left) and ORAS (right) can be seen in the following images (ORAS requires to skip 2 cutscenes, of which only the second matters):

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed7.png)

I skipped at frame 300 which is an easy number for me to remember.

Freeze the game at the "Continue screen" and press "Update" in CitraRNG.

In Tiny Finder, go to -> Extra -> MT RNG -> Seed RNG and fill in the boxes.

My target seed is FFFFFFFF, target date is 2022-05-23 and the other 2 values (Frame 300 Seed and Save Parameter) I read them from CitraRNG.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed2.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed3.png)

The results in Tiny Finder show that after pressing 'A' to load the save file, 
if I save the game at frame **12476**, my new Save Parameter will change to **79913DDC**.

If done right, all I will have to do, is reload Citra at date **2022-05-23T15:07:11** as shown in the tool, 
and if I skip the cutscene at the same frame number (300) I did earlier, I will hit my target seed.

Let's get this done, I need to save at frame 12476.

**Important: In gen 6 no matter what CitraRNG shows, frames advance by 2 in most cases. 
This means that if my current frame type is odd (1, 3, 5 etc), I can only hit odd frames and if it's even (2, 4, 6 etc) I can only hit even frames.
This can be confusing because if my current frame type is odd 
I can't hit frame 12476 which is my target and I will either hit 12475 or 12477 so I need to check my frame type and change it if necessary.**

### Finding the current frame type

Just go to the save option (Yes/No), freeze the game and start advancing slowly 1 by 1.

Pay attention to the red box that highlights the option and check when it moves (you will see it getting bigger/slower as frames advance).

I notice that the animation happens in odd frames so I need to change my type before actually saving.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed4.png)

### Switching between the 2 frame types

Inside the bag, frames actually advance 1 by 1 so it's easy to control them and land on the correct type depeding on the frame you exit.

If you want to land on odd frames, exit the bag at an odd frame and vice versa.

To do it correctly, freeze the game and hold the 'X' button to exit from the bag to the overworld.

Since my target frame is 12476 (even), I freeze the game at frame 10000 (even) and exit the bag.

All I need to do now is just save the game at frame 12476 and I expect my Save Parameter value to change from **67181505** to **79913DDC**.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed5.png)

There we go, almost done.

Close the game and copy paste the New Date from Tiny Finder to Citra (2022-05-23T15:07:11) in my case.

Load the game again and skip the final cutscene at the same frame number you did earlier (as said I always use frame 300 to remember it easier).

If everything done right will hit your target seed inside the target date (May 23 2022) and be ready to go.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed6.png)


# Seed RNG - Specific Date + Time

**Before proceeding, please make sure that you have understood the above method first.**

The only reason to combine a specific MT seed with a specific date + time, is for abusing both the MT and TinyMT seeds simultaneously.

This can be useful when you want to RNG a very specific DexNav encounter with specific PID for example.

You can either right click inside the target TinyMT index in the main form and have it set the MT window for you, 
or just put the Target date and time manually.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed8.png)

Set the Citra RTC to the target Date + Time (in the previous method we set the time to 00:00:00) and for once again,
load the game and skip the final cutscene in a frame of your choice, 
copy and put the initial seed and current Save Parameter from CitraRNG to Tiny Finder and click "Search".
It will take a few seconds/minutes to find a result, don't worry.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed9.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed10.png)

Now things are getting a bit tricky.

Close the game and in Citra menu, set the RTC to the new Date shown in the tool (**2022-06-06T00:23:59 in my case**).

Load the game and skip the final cutscene at the same frame you did earlier.

If everything is done right, your actual (temporary) Initial Seed will be the one shown in the tool (**44F06FFF in my case**).

Load the save file and like we did in the previous method, 
you 're gonna have to save the game at the frame shown in order to obtain the New Save Parameter.

(In my case, I need to save at frame **7189** and the Save Parameter will change from **79913DDC** to **82AE86D2**)

In the previous method, we also explained how to deal with the odd/even frame issue so make sure you have understood that part first.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed11.png)

Success!

My new Save Parameter value is the correct one and now all I need to do, 
is change the Citra RTC to the desired Date + Time again and skip the final cutscene at the same frame I did earlier.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/MT%20Seed/Seed12.png)


















