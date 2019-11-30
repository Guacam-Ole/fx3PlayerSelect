# FX 3 PlayerSelect

## What this does
This is a simple little "Mid.Launcher" - Application that allows you to select how many players you want to play on FX3 Pinball tables if you run in Cabinet mode without having to go through the options. 
(1 Player starts the "normal" mode, 2-4 the according "Hot Seat" - Modes)

## What you need
This is meant to be used in combination with a launcher like PinballX

## Configuration
You need to change your launcher application to use Fx3PlayerSelect instead of Steam. The following should work on other launchers, too:


### PinballX
First of all change the launcher from Steam to the PlayerSelect. You can do this in the Config-Tool, or edit the `PinballX.Ini` instead. When you have successfully created a running cabinet you should be familiar with config files by now :)

Look for `[PinballFX3]` and change the workingPath and Executable:
```
[PinballFX3]
WorkingPath=C:\pinball\FxPlayerCount
Executable=PlayerSelect.exe
```

Remember the workingPath and Executable before and do **NOT** change any other setting. This tool WILL work in the Steam-folder btw but I am unsure if that would survive a steam-update, so better be safe than sorry.

### PlayerSelect-Config
Currently you have a lot of options in the PlayerSelect.exe.config. We will go through them

(Hint: You can test all the settings, espacially the window position directly by starting the application. The only difference is that when selecting a player Steam launches instead of Pinball FX.)

#### Steam location
First of all you should change the value in `Launch' and change it to your Steam-Location
<add key="Launch" value="C:\pinball\steam"/>

#### Screenlayout
Now everything should already work. But most likely you want do make changes so it fits your screen layout.
Change the following settings so Orientation, Position and Sizes of your main Monitor are met:
```
<add key="WindowWidth" value="1500"/>
<add key="WindowHeight" value="600"/>
<add key="WindowX" value="100"/>
<add key="WindowY" value="200"/>
<add key="Rotate" value="180"/>
```
Rotate really only makes sense with 0,90,180 or 270. Other Values might have an effect, but maybe not the wanted :)

#### Theming
The following options are just there to be able to change the style to your needs. The following values should be self-explanory. If you leave the "WindowImage" empty, the program can work in transparent background mode.
```
<add key="WindowBackColor" value="Transparent"/>
<add key="WindowImage" value="selectback.jpg"/>
<add key="BackColor" value="Black"/>
<add key="ForeColor" value="White"/>
<add key="HighlightBackColor" value="Yellow"/>
<add key="HighlightForeColor" value="White"/>
<add key="FontSize" value="24"/>
<add key="FontStyle" value="Tahoma"/>
<add key="Width" value="200"/>
<add key="Height" value="40"/>
<add key="Label1" value="1 Player"/>
<add key="Label2" value="2 Players"/>
<add key="Label3" value="3 Players"/>
<add key="Label4" value="4 Players"/>
```
Colors can be one of the following: https://docs.microsoft.com/en-us/dotnet/api/system.drawing.knowncolor?view=netframework-4.8
or simply enter the HEX-Code like
"FF0033"

#### Mapping
You can of course change the mapping for Up/Down and Select:
```
    <add key="KeyUp" value="LeftShift"/>
    <add key="KeyDown" value="RightShift"/>
    <add key="KeySelect" value="Enter"/>    
``` 
The Keynames can be found there: https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.key?view=netframework-4.8
You can use the name or the int-value


# Warning
A word of warning: There is nearly no error handling. While everything works fine without issues better do not enter invalid values into the config (like "hello" where a number was expected)

# Have fun
That should be it. If you have any question/bug/feature request: Open an issue here.

Ole
