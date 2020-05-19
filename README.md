# Astral Chain Load Remover/Autosplitter
This is a Video Auto Splitter Profile which acts as an Autosplitter for Astral Chain Any% This goal of this tool is to provide runners with a standardized set of splits and split times. This allows for runners to split for every main section of the run without having to do so manually, and will give a more detailed view of where you can save time.

## Table of Contents
* [Features](#features)
* [Required Programs](#programs)
* [Setup](#setup)
* [Known Issues](#issues)
* [FAQ](#faq)
* [Credits](#credits)


## Features <a name="features"></a>
* Automatic timer start upon confirming character selection. The timer starts a bit later than this button press, but it adjusts the start time accordingly.
* Automatic splits for case completion screens.
* Automatic splits on black screen after ending a file.

## Required Programs <a name="programs"></a>
Download the the latest verison of the Autosplitter on the release page [here!](https://github.com/KiernanBrown/AstralChainAutosplitter/releases/tag/v0.1) In addition, you will also need the following two programs:
- [Virtual Cam Plugin for OBS](https://obsproject.com/forum/resources/obs-virtualcam.539/) This plugin is necessary if you are using OBS, as it allows livesplit to access a feed of your capture card. If you are using XSplit, you can use the Virtual Camera that it provides instead.
- [Video Auto Splitter LiveSplit Component](https://github.com/ROMaster2/LiveSplit.VideoAutoSplit) This is the core component that allows the Autosplitter to function.  

Both of these have their own setup instructions which can be found on the sites listed above. Please follow these setup instructions before moving on to the setup for this specific profile below!  


## Setup <a name="setup"></a>  
As mentioned above, please download the latest version of this Autosplitter [here!](https://github.com/KiernanBrown/AstralChainAutosplitter/releases/tag/v0.1)
A tutorial video for setting up this Autosplitter can be found here so follow along with it: 

[![Thumbnail for YouTube tutorial video](http://img.youtube.com/vi/hbCzEasFT6k/0.jpg)](http://www.youtube.com/watch?v=hbCzEasFT6k "tutorialIMG")  
[https://www.youtube.com/watch?v=hbCzEasFT6k](https://www.youtube.com/watch?v=hbCzEasFT6k)

For this current version, **make sure you don't adjust the number of splits in this splits file!** The Autosplitter is designed to split at every file end and every time the case completion screen is shown, and will continue to do so even if you remove splits from the file. Feel free to rename splits as you want, just don't add or remove segments!

For the game itself, make sure that your brightness is set to 5. Modifying the brightness can affect some of the image recognition for splitting and can result in false detections for loads by making blacks darker or whites lighter.

If you are having issues with the setup for this, feel free to send me a message on Discord (SwiftShadow#5004) and I can help troubleshoot!

## Known Issues <a name="issues"></a>
* The Autosplitter can split twice on the first split of the run for some reason which I can't figure out. I have code written to prevent double splitting, but it still happens. For now, just undo a split if it does split multiple times. I'll continue looking into this for the future.
* The Autosplitter has a chance to miss a split if the Lappy image comes in late (it happens sometimes, which I wasn't aware of before). I am working on a fix for this now which should be finished soon. If a split is missed, you can skip it and the Autosplitter should continue to function. If the Autosplitter misses multiple splits in a row, **please check the error log and send it to me** as noted in the FAQ below. This most likely means the Autosplitter crashed and having access to the error log would help me to debug it. If this does happen, you can switch to splitting manually for the rest of the run and continue as normal.

If you find any issues that are not listed above, please let me know about them by sending me a message on Discord!

## FAQ <a name="faq"></a>
* [I cannot run the Autosplitter and stream at the same time. What do I do?](#not-running)  
* [Why does Cerberus split in a weird spot?](#cerberus)  
* [The Autosplitter stopped splitting mid run. What happened?](#crash)  

### I cannot run the Autosplitter and stream at the same time. What do I do? <a name="not-running"></a>
Unfortunately, using a Video Auto Splitter like this is pretty CPU intensive, so not everyone will be able to run this. I am currently working to improve performance of this, but the changes that I can make will probably have minimal impact. If you are unable to run this, I'm very sorry!

### Why does Cerberus split in a weird spot? <a name="cerberus"></a>
The Cerberus split is different from other splits in the run as it uses the case completion screen as a dummy to check when the fight has been completed, but it actually splits on a black screen fade out when you reach Isabella. The Cerberus fight "technically" ends upon dealing the last hit to Cerberus, but unlike other fights in the run, your ending position on this fight matters quite a bit as you have to chain jump over to Isabella after the fight is over. It makes more sense to have the split end upon reaching Isabella so the starting time for the next split is always consistent, rather than dependent on where you kill Cerberus and how long it takes you to get over to Isabella.

### The Autosplitter stopped splitting mid run. What happened? <a name="crash"></a>
First off, I'm extremely sorry if this does happen! In the event that it does, you can switch to manual splits for the rest of the run. Once you finish your run, it would be greatly appreciated if you could export the log and send it to me on Discord!
  
Secondly, I'm not exactly sure why this is happening, but it is a known issue for this profile and others that I have used (KH3 Load Remover). This seems to only happen during long stretches of use, so try and make sure that you aren't leaving LiveSplit open too long and idling before doing a run. Also, try checking the error log for the Video Auto Split component in your layout before you start a run (Right Click -> Edit Layout -> Layout Settings -> Video Auto Split). If you do see an error there, export the log and send it to me on Discord, and then restart LiveSplit to see if it fixes itself.  
  
In the event that you do experience any issues with a problem similar to this, please export your error log as mentioned above and send it to me so I can take a look at it and hopefully work to resolve this!

## Credits <a name="credits"></a>
* ROMaster2 - Creation of the Video Auto Split Component. Also, his example profiles of Splatoon 2 Octo Expansion and Super Mario Sunshine helped immensely with developing this profile.
* Denhonator - Inspiration for the creation of this profile and code for the loading screen buffer.
* IddyBTW - Testing and image gathering for load screen removal.
* You - Seriously, thank you for taking the time to test this out! The more people we have testing this, the faster we can fix issues and make sure that everything is as accurate as it can be.
