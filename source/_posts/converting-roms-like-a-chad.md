---
title: Converting roms like a Chad
date: 2022-06-17 20:07:42
categories:
- Tech
tags:
- Personal Interest
- Software
---
Here the promised article about properly converting roms from different consoles into smaller formats or formats that will match different datted rom sets.
Took me a while to get to this article because i moved into my new flat :)

This one is my [**favourite tool**](/assets/18-06-22/Cue+Bin-&-Iso-CHDConverter.zip), it converts all Disc based media into the .CHD file format. It is extremely space saving and could easily half your Disc based rom collection, it is also completely reversable, and the tool used for it is the **chdman.exe** which is included by MAME, make sure to download MAME, then extract it and copy the newest version into this tool. This has the potential to result in even smaller files in the future.

-> The tool includes a **CUE or GDI to CHD** script, a **ISO to CHD** script and a script to reverse the CHD file back to the CUE-BIN format, you could modify the last script to result in a ISO file.

This second [**tool**](/assets/18-06-22/NDecrypt.zip) is for En-/Decrypting Nintendo DS roms, using this tool the resulting file will match to the No-Intro DS sets. It can also EN-/Decrypt matching 3DS & DSi titles, you will have to provide your own keys.bin which i cannot share with you.

-> You will have to modify the two .exe files and set the path to a roms folder in which the files are placed which are to be converted.

The third [**tool**](/assets/18-06-22/DS-&-3DS-Decryption-&-Trimming-Tool.zip) can Decrypt 3DS roms without the need of a key.bin. These Decrypted files will *not* match the No-Intro dats. A readme is included.

-> This tool can reduce the size of your NDS, DSi & 3DS roms by trimming them, this can greatly save space but will not match *any* set due to obvious reasons.

[**Tool**](/assets/18-06-22/3DS-+-CIA-Rom-En-Decrypt-Script.zip) number four can En-/Decrypt 3DS roms which will match the No-Intro sets, it can also convert CDN games to CIAs and convert a bunch of other 3DS files to a different file type.

The last [**tool**](/assets/18-06-22/NKit-Converter.zip) on my list is the NKit converter, NKit is a file format commonly used on Gamecube and Wii ISOs. Dolphin, a emulator for these consoles has a better file format included which is .RVZ, make sure to use it, because it has the highest compression ratio and can revert back to the original ISO, this tool comes in handy if you have NKit files on your drive and want to convert them back.

-> Fun fact, the RVZ file format was also developed by the NKit developers.

Make sure to mention noteworthy tools in the new comment section below and i will take a look at them & perhaps add them.

Have a great rest of your weekend and have fun with the tools. :D