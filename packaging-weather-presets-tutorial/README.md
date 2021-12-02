# Packaging Weather Presets Tutorial

This is a tutorial on how to package a simple MSFS2020 weather preset pack to place in the Community folder.

In preperation, grab the very useful tool named `MSFSLayoutGenerator.exe` which takes the leg work out preparing layout files [from here](https://github.com/HughesMDflyer4/MSFSLayoutGenerator/releases/). Get the latest .EXE and store where you like, I have it on my desktop so I can just drag layout files to it. The main project repo [is here](https://github.com/HughesMDflyer4/MSFSLayoutGenerator).

This tutorial doesn't cover making new weather presets themselves but you might find the documentation [found here](https://docs.flightsimulator.com/html/index.htm#t=Content_Configuration%2FFlights_And_Missions%2FWeather_Definitions.htm) to be useful. It can be misleading at times as the docs do not always match what the current version of the sim is capable of.

1. Create a new folder to store your project(s) in, in this case I've called it `CommunityProjects`.
2. Within this folder create a folder for your first weather preset pack. I've called it `my-weather-presets`. This will be the top level folder that you place in your Community folder so think about the name. But best practice seems to be all lower case with words seperated by hyphens and the first word to be the creator (you).
3. Within this folder create a file named `layout.json` (it can be empty at this stage).
4. Also create a new file named `manifest.json` and [use the contents of this file](https://raw.githubusercontent.com/DoNotBeOnFire/msfs2020-weather-presets/master/packaging-weather-presets-tutorial/manifest.json) as a template. Modify the values for `title`, `manufacturer`, `creator` to personlise to your needs (Note. Tools like MSFS Add-on Linker that many people use to manage Community mods will read and display these values).
5. Also modify the `package_version` to suit your versioning system, e.g. start at `1.0.0` and for each subsequent release increase the value, e.g. to `1.1.0` for a minor release or to `2.0.0` for a major new update.
6. And finally modify the `minimum_game_version` usually to what version of the game you are developing on currently. Not quite so important with MSFS2020 as you have no choice whether to update versions.
7. Save the `manifest.json` file.
8. Create a new folder here named `WeatherPresets`. This name is mandatory and case sensitive.
9. Within this folder place your .WPR files. In this tutorial, I'll place two weather presets there named `Atmospheric.WPR` and `ConvectiveDay.WPR`

So within your `CommunityProjects` folder you should have a single folder named `my-weather-presets`. Within that folder should be files named `layout.json` (empty) and `manifest.json` and a folder named `WeatherPresets`. The `WeatherPresets` folder should contain only .WPR files and in this case two files named `Atmospheric.WPR` and `ConvectiveDay.WPR`

10. Navigate to the folder `my-weather-presets`.
11. In another window, navigate to where you stored the application `MSFSLayoutGenerator.exe`.
12. Drag-and-drop the file named `layout.json` on top of `MSFSLayoutGenerator.exe` (you'll see a small window quickly pop-up and disappear again).
13. If you open `layout.json` you'll note there are two entries for the weather preset files `Atmospheric.WPR` and `ConvectiveDay.WPR` with file sizes and date strings (File Date format).
14. If you open the `manifest.json` file you'll note the addition of the `total_package_size` entry.
15. Copy the folder `my-weather-presets` into your sim's `Community` folder, fire up the sim and ensure your presets are appearing on the weather presets list. If there are any issues, ensure you don't have any duplicate presets elsewhere in the `Community` folder or elsewhere in the sim.
16. If you intend to share the preset package with others or to upload to somewhere like [flightsim.to](https://flightsim.to/) it is usually best to create a ZIP file and add the folder `my-weather-presets` to it (rather than the contents of that folder). That way, unZIPping it gives you a drag-and-drop folder named `my-weather-presets` to place into the `Community` folder.