# Astral Chain Load Remover/Autosplitter
This is a Video Auto Splitter Profile for Astral Chain Any% The goal of this tool is to present a better timing method for Astral Chain Any% runs, which will remove inconsistent load times and lessen the gap between the physical and digital versions of the game.

## Table of Contents
* [Features](#features)
* [Required Programs](#programs)
* [Setup](#setup)
* [Known Issues](#issues)
* [FAQ](#faq)
* [Credits](#credits)


## Features <a name="features"></a>
* Load removal for black screen loads, white screen loads, astral plane loads, and loads for transitioning between zones. The only known additional load times that are not being removed are the elevators up to the roof in Rayleigh Plaza, where the Digital Version saves about 4 seconds total across the run over the Physical Version.
* Automatic timer start upon confirming character selection. The timer starts a bit later than this button press, but it adjusts the start time accordingly.
* Automatic splits for case completion screens.
* Automatic splits on black screen after ending a file.

## Required Programs <a name="programs"></a>
- [Virtual Cam Plugin for OBS](https://obsproject.com/forum/resources/obs-virtualcam.539/) This plugin is necessary if you are using OBS, as it allows livesplit to access a feed of your capture card. If you are using XSplit, you can use the Virtual Camera that it provides instead.
- [Video Auto Splitter LiveSplit Component](https://github.com/ROMaster2/LiveSplit.VideoAutoSplit) This is the core component that allows the Autosplitter to function.  

Both of these have their own setup instructions which can be found on the sites listed above. Please follow these setup instructions before moving on to the setup for this specific profile below!  


## Setup <a name="setup"></a>  
A tutorial video for setting up this Autosplitter can be found here so follow along with it: [![Thumbnail for YouTube tutorial video](http://img.youtube.com/vi/hbCzEasFT6k/0.jpg)](http://www.youtube.com/watch?v=hbCzEasFT6k "tutorialIMG")  

In LiveSplit, be sure to compare against Game Time instead of Real Time. The load remover only pauses the timer for Game Time, so if you're comparing against Real Time, it'll look like it's not working. This also allows you to set up two timers (one Game Time, one Real Time) to have both RTA and RTA with loads removed on your set of splits! 

Also, if you are using the Autosplitter, make sure you don't adjust the number of splits in this splits file! The Autosplitter is designed to split at every file end and every time the case completion screen is shown, and will continue to do so even if you remove splits from the file. Feel free to rename splits as you want, just don't add or remove segments!

For the game itself, make sure that your brightness is set to 5. Modifying the brightness can affect some of the image recognition for splitting and can result in false detections for loads by making blacks darker or whites lighter.

If you are having issues with the setup for this, feel free to send me a message on Discord (SwiftShadow#5004) and I can help troubleshoot!

## Known Issues <a name="issues"></a>
* The Autosplitter can split twice on the first split of the run for some reason. I'm looking into this now.  

If you find any issues that are not listed above, please let me know about them by sending me a message on Discord!

## FAQ <a name="faq"></a>
* [I cannot run the Load Remover and stream at the same time. What do I do?](#not-running)  
* [My timer does not pause immediately on loading screens, and it ticks a bit when changing from a black load to transition load, or astral plane load to white load. What's wrong?](#loads)
* [Why does Cerberus split in a weird spot?](#cerberus)  
* [My timer stops removing loads and splitting mid run. What happened?](#crash)  

### I cannot run the Load Remover and stream at the same time. What do I do? <a name="not-running"></a>
Unfortunately, using a Video Auto Splitter like this is pretty CPU intensive, so not everyone will be able to run this. I am currently working to improve performance of this, but the changes that I can make will probably have minimal impact. If you are unable to run this, I'm very sorry, but it isn't too big of an issue in the grand scheme of things! At this point in time, this Load Remover is experimental and is not necessary for submissions to the leaderboard. In the case that this timing method is used in the future, other moderators or community members would be able to retime your run to remove loads as long as you are able to provide a clean video of your run (through either a local recording or stream highlight).

### My timer does not pause immediately on loading screens, and it ticks a bit when changing from a black load to transition load, or astral plane load to white load. What's wrong? <a name="loads"></a>
This is working as intended! Right now, the load remover has a 6 frame buffer where it waits before pausing the timer to help prevent false load detection. In other words, the load remover waits until it has recognized a loading screen for 6 consecutive frames before pausing the timer. This also results in the timer ticking forward a few fractions of a second when moving between two different kinds of loading screens. Everyone using this load remover will experience these same periods of time where the timer is not paused. Although this isn't removing 100% of the load times, this approach offers much more consistency and accuracy than trying to pause on the first frame of every load.

### Why does Cerberus split in a weird spot? <a name="cerberus"></a>
The Cerberus split is different from other splits in the run as it uses the case completion screen as a dummy to check when the fight has been completed, but it actually splits on a black screen fade out when you reach Isabella. The Cerberus fight "technically" ends upon dealing the last hit to Cerberus, but unlike other fights in the run, your ending position on this fight matters quite a bit as you have to chain jump over to Isabella after the fight is over. It makes more sense to have the split end upon reaching Isabella so the starting time for the next split is always consistent, rather than dependent on where you kill Cerberus and how long it takes you to get over to Isabella.

### My timer stops removing loads and splitting mid run. What happened? <a name="crash"></a>
First off, I'm extremely sorry if this does happen! In the event that it does, please finish your run as it can be retimed after the fact. You might also want to switch to comparing against Real Time in that case so your splits will show times without load removal for the rest of the run. Once you finish your run, it would be greatly appreciated if you could export the log and send it to me on Discord!
  
Secondly, I'm not exactly sure why this is happening, but it is a known issue for this profile and others that I have used (KH3 Load Remover). This seems to only happen during long stretches of use, so try and make sure that you aren't leaving LiveSplit open too long and idling before doing a run. Also, try checking the error log for the Video Auto Split component in your layout before you start a run (Right Click -> Edit Layout -> Layout Settings -> Video Auto Split). If you do see an error there, export the log and send it to me on Discord, and then restart LiveSplit to see if it fixes itself.  
  
In the event that you do experience any issues with a problem similar to this, please export your error log as mentioned above and send it to me so I can take a look at it and hopefully work to resolve this!

## Credits <a name="credits"></a>
* ROMaster2 - Creation of the Video Auto Split Component. Also, his example profiles of Splatoon 2 Octo Expansion and Super Mario Sunshine helped immensely with developing this profile.
* Denhonator - Inspiration for the creation of this profile and code for the loading screen buffer.
* IddyBTW - Testing and image gathering for load screen removal.
* You - Seriously, thank you for taking the time to test this out! The more people we have testing this, the faster we can fix issues and make sure that everything is as accurate as it can be.