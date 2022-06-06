---
title: How i resurrected the oldest minecraft mod
date: 2022-06-06 23:30:09
categories:
- Tech
tags:
- Personal Interest
- Software
---
I want to write this article because preserving Video Game history is very important to me and encouraging other people to do as i do for a good cause does have next to no negatives. Are you like me and like to play retro games, do you find yourself looking on shady sites to find a copy of Super Mario World for the SNES just to download a .exe file which contains malware? Want to patch a game with a translation patch or a rom hack but the rom you've got does not work for the patch? This can be because it's corrupt or the rom requires a different **hash**. More on hashes later! Ever find yourself struggeling with managing the names in your massive rom library you have dumped / collected from deep places of the web? Boy have i got a solution for you!

## The Datting scene

### Origins

Since as early as the 90s the video game emulation/preservation group *MAME* has used so called DATS to scan good dumped ROMS against them to verify wether or not they match, this way you know that the file you have has not been tempered with in any way. This has over the years led to many DATTING-Groups to find their way into the world, three of the most noteworthy are:

TOSEC: [Datting since 2005, both Digital & Analog Media](https://www.tosecdev.org/)
REDUMP: [Also Datting since 2005, the goto source for Disc Based Media](http://redump.org/)
NO-INTRO: [Datting since 2002, the goto source for Digital, Cartridge & CDN (Content Delivery Network) Media](https://datomatic.no-intro.org/)

Now that we know, that you can get specific DATS for different consoles, you may ask: "But Ryuu, what do i do with it?" _**RomVault.**_

### One Tool to manage them all

![](/assets/05-06-22/romvault.png)

At this point you first have to ask yourself, do i just want to manage the roms that i've got or do i want to expand to different consoles and spend more time collecting games than actually playing them?

This is a realization i had when i had about 80TB of roms on my RAID. Made a decision? Alright lets move on.

Download the newest version of [RomVault](https://romvault.com/), make sure to extract it on a fast drive (this matters because of frequent Caching), not an HDD, your roms can be stored on a drive outside of RomVault.

Your folder will look something like this excluding the Cache files:

![](/assets/05-06-22/romvault-structure.png)

I am sure you noticed the DatRoot Folder. This is where you can put your DATS into manually, there is a better solution though, to which we come back later.
The ToSort folder is the folder in which you are gonna move your roms, isos and other kind of files into, which you want RomVault to sort.
You should also have a DatRoot folder, this is where the roms will get sorted into, you can configure the location of the DatRoot folder in the RomVault settings or the cfg.xml.

Upon starting this is what the interface looks like:

![](/assets/05-06-22/romvault-interface.png)

Next thing we will want to do is to activate "Convert all zips to trntzips" under *Settings -> RV Settings*, while at it, you can also change your DatRoot location, if you want to do that:

![](/assets/05-06-22/romvault-rvsettings.png)

The following are probably the most important settings for you, you can set your RomRoot to whatever location you please, be it a small 1TB external HDD or a Petabyte Server with ZFS File Deduplication. Under Archive Type, you can either choose zip or 7z, below that are a few settings you'd be interested in if you want to store your MAME set, you know what to choose if you already want to setup MAME :P
If you only plan to store a few smaller sets and not whole 23,5TB PS2 ISO images, then make sure to choose **Single Archive**, this will make sure to put all your zipped roms into one big zip and thus saving some space, on the contrary extracting takes one more step.

![](/assets/05-06-22/romvault-directory-settings.png)

All setup? Do you have the Dats you need in the DatRoot? If not jump to the **DatVault** section if you plan to automate updating your DATS.
The next part requires a doctor title, to perform sorting & hash checking of your roms. Press these buttons in descending order and watch it do it's work with every step.

![](/assets/05-06-22/romvault-steps.png)

There are different hash alghorithms, just to name a few: "CRC32, SHA1, MD5". A hash is a value which is defined by it's ones and zeroes, if one is off, the file is different and thus has a different hash, thus won't match to your set. Don't touch those filthy files if you see them!

Now you are a computer wizard. Check your RomRoot folder for your games, if everything went well, most if not all of your roms should be sorted into it's respective set & be renamed.

-> If there are still files in ToSort, that can either mean they don't match to any of these sets (being dumped wrong or being a corrupt file can be the cause), or you haven't got the according DAT for that platform. With how easy it is, this can very quickly grow into an addiction, just make sure to check your countries laws on downloading copyrighted media for personal consumption, this can very well be allowed as long as you dont share your files, i am not the one to judge where you get your files from and if you break any laws, i did my part warning you :P

![](/assets/05-06-22/romvault-datahell.png)

### DatVault

I have been updating Dats manually for years. But last December DatVault released, and if you are a hoarder like me, you'll love & appreciate it just like me. This is how to get there:

![](/assets/05-06-22/romvault-datvault.png)

Here's the part you'll not gonna like to hear, it's gonna cost money. You'll have to support GordonJ on Patreon for his incredible work.
The benefits are daily one click Dat updates, ability to easily add new released Dats and even some custom Dats like the DeDupe ones which you can use for sets like the Dreamcast, GameCube or the Phillips CD-i across Redump, No-Intro & TOSEC to make sure those large .iso files don't have to be put into two folders(Which is irrelevant if you use ZFS file deduplication on your server).

![](/assets/05-06-22/romvault-datvault-interface.png)

### Where do i get good roms mister Ryuu?

Because of legal reasons i can only advise you to dump them yourself, i am not allowed to directly provide you with a link to roms, but rumours have it that one or more of these Datting Organizations could be found on the [Internet-Archive](https://archive.org/details/software). no. STOP!!!
