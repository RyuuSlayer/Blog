---
title: How i resurrected the oldest minecraft mod
date: 2022-06-06 23:30:09
categories:
- Video game
tags:
- Personal Interest
- Software
- Development
---

The year is 2010, development on a Minecraft Mod called **AdventureCraft** has started. The one to write the mod is a man named Cryect. He worked with a few other people to create the biggest and most creative mod of the time and released it on the [Minecraft Forum](https://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/1272366-1-3-2-adventurecraft-npc-pathing-blocks-r1095).
But what makes it so special I hear you ask. It adds a special Debug mode which lets you create your own story through Trigger based blocks which activate when the player walks through them, thus doing whatever the Map Creator intended it to do through scripts. This opened the door to easily telling your own story through connecting a few of these Triggered Blocks, which the person playing can't see in Adventure mode.

<iframe width="720" height="480" src="https://www.youtube.com/embed/CQSxxKkUP3s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

In 2011 then, development stopped, Cryect disappeared, a few years later he uploaded a Video on his YouTube channel showing a VR game he made in his job as it seems. He didn't answer anything related AdventureCraft on his personal Twitter. AdventureCraft's community shrank and we find ourselves back in 2017 where my role found it's start. I knew the mod from back then & had nostalgic feelings for it, not long after I found a download and a few maps for it.

Let me tell ya, this is where the fun begins, the state in which AC was left... not a good one. It didn't run on 64bit systems and the 32bit it supported, it didn't do a good job at. The server for it's original launcher also didn't exist anymore. The iceing on the cake, you had to start it through a crappy .bat file which not long after got detected by Windows Defender on basically every up to date system.

I went ahead and made it run on 64bit systems, this allows it to use more than 4GB's of RAM, because it is a JAVA Program, there were ways of optimizing it's startup variables for Garbage Collection, which Ii did. This resulted in smoother gameplay. I didn't stop there, AC had a few game breaking flaws on AMD Gpu's which I have patched (I also made it so boats drop themselve instead of giving you wood & sticks just like in the BETA Version it is based on [B1.7.3](https://minecraft.fandom.com/wiki/Java_Edition_Beta_1.7.3)).

Alright, it's not as horribble as it was, **I thought** and made a simple website for people to download it & some of it's maps.

The year is 2018, here in germany you can do the so called Abitur after 10 years of school or decide to go to a profession specific school, I did the latter and went to IT school. We had a year long group assignment to code / create something in a team, so i decided to remake AdventureCraft and my friend in class had the plan to create a new launcher for it with a website to download the maps from. (We also had a 3rd member who didn't contribute, who later got an "what would be equivalent to a **F**" in america). Quite the ambitious project, we actually had to fight for the possibility to even be allowed to do this, it also seems to have been too ambitious for our teacher at the time.

This is where the actual pain begins. **MCREATOR** a software to aid you making mods, as someone who had no clue about the modding world I opted for this tool, after 3 months of working on it with assistance of my classmate, called **SirBlock** on the official AC Discord, we decided that MCreator is no good for this task, we were limited by the tool and would have to wait months for it to update & play catchup with the actual Minecraft Version.

This is when i found [**TaleCraft**](https://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/wip-mods/2631866-talecraft-a-mod-for-more-custom-and-advanced), a continuation by Tiffit & Longor, the latter one i got in touch with, he allowed me to continue the work on the Mod. As of today it is stuck at 1.12.2, we dropped this later on in our journey simply because it was unfeasable to update it, 1.12.2 had massive refactors on both Minecraft & the Forge Source code, which would require a massive rewrite, and as time went by this has been a good decision, because we would have to do it not only once. (Great thanks for Longors monetary support on Patreon, he was very generous and we would have stopped long ago if it wasn't for him: "Servers had to be paid")

Alright, nearly time to present our project, SirBlock made the launcher & the [website](https://adventurecraft.gq/) and both worked just fine (They have been refactored quite a few times to date). Around that time we actually got approved for the Discord Developers Program & having our Launcher be in Discords Game section:

![](/assets/06-06-22/ac-discord.png)

Back then you could even have a shop on your Discord, we planned to make the maps available for there as well. Sadly we got yeeted and deleted a week after that, without a explanation :/ After explaining that we didn't sell Minecraft nothing changed. Well atleast they refunded my 20€ for applying to the developers programm ;D

I did my part in fixing a few issues TaleCraft had and made it be more like AdventureCraft than a continuation, people like familiarity, which later proved itself when i tried to release a completeley reprogrammed version and about 20 people started it in a span of 3 months. _**Ouch**_ Let's skip this part.

Now we had the chance to present our project. We obviously got an **A** each, except for guy number three. Here's a [video](https://youtu.be/0pj2_brhg6A) showcasing a few of it's features (I had a bad PC).

In the year to come i went through the Internet Archive and looked for maps that have been lost to time, got about 45+ GB's. Most of em not worth uploading to the website because we have to pay for the Server. This is also when demand on the server went up by alot, we couldn't have handled it without the support we got by Longor & our dear [Patreons](https://www.patreon.com/AdventureCraft).

Oh boy 2019. One day suddenly alot of people joined our official Discord and threatened us to sue or even kill us, while most of it just words by a angry internet mob, they certainly weren't all wrong. The problem with AC is that it is a .jar mod made with MCP, you are suppoused to open the minecraft.jar which you legally obtain by downloading it with a valid account, then deleting the METAINF file in it's jar and dropping the MCP mod into it.

Alright, lesson learned, but what solution do we have, we cannot take the mod out of the .jar, AC was made in a strange way in which 2 jars were chained together, and both contained both vanilla and modded files.

First thing we did was requiring people to be logged into the vanilla launcher, thus already making sure they can't play if they don't have a legal version of the game.

Second thing we did was reverse engineering the [**AC source code**](https://github.com/RyuuSlayer/AC-1.7.3) through decompilation, this happened between Juli 2021 through January 2022. AC was effectively licensed under Creative Commons by Cryect, bummer that he never actually released the source code, we later had people complaining that we cannout use MCP source code in the decompiled version, early versions of MCP didn't have a license thou.

Through reverse engineering the mod, and not keeping a single line of original mappings (class & field names in java), and no part of Mojang code in it, we effectively had new code that was ARR (All rigths reserved), i relicensed it with the permission of the two people who worked on this with me to GPLv3. We went on to put the mod on cursed-fabric, a fabric version of BETA 1.7.3.

The guy who stayed in the development team **TechPizza** is a programming genius, we couldn't have decompiled the project without him, this literal GigaChad writes his own Voxel Game Engine in his freetime. He is working on porting all of AC into his own engine and de-minecraftifiying it, in like 3 days he wrote a world compression format that made 550~ish megabytes be 6 megabytes. Then went on to create all of [**this**](https://www.youtube.com/watch?v=5Ojxl70fjYo) the same day. Not only does this guy have a bright future, but also does AC. Im sure i will be writing a follow up Article on how development on the standalone AdventureCraft is going.

If you aren't convinced to try this mod out, watch this:

<iframe width="720" height="480" src="https://www.youtube.com/embed/9Sm0pmBx4oI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>