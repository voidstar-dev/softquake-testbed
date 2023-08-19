==============================================================
Testbed for SoftQuake
==============================================================
What is SoftQuake?

SoftQuake was started by me in July 2023 as a way to play Quake using the software renderer
without needing to emulate it through DOSBox.

I started with the original source code release found here:
https://github.com/id-Software/Quake

Over a period of about 1 week I developed a good foundation for a cross-platform port of the game,
and have been making minor adjustments since.

If I may compare this project to anything, I'd probably say that in spirit it's similar to Chocolate Doom.
That is, leave the base game untouched, and don't add any new gameplay/engine features.
If you enjoy playing Chocolate Doom, chances are you will enjoy the SoftQuake port as well.

Finally, I have also ported the original GLQuake version, but this is a topic for another time.


==============================================================
Primary goals
==============================================================
-- Don't touch the rendering code. Leave the visuals exactly as they were upon release

-- Cross-platform/OS support. 
   Currently the code compiles on Linux (GCC) and cross-compiles to a Windows executable using MinGW
   Other platform support contributors are welcome

-- No additional quality of life features (except in dealing with video resolutions and input)


==============================================================
What works
==============================================================
-- The base game
-- Mods/map packs
-- Audio (SFX)
-- Emulated CD audio (needs a ripped tracklist)
-- Keyboard/mouse input
-- Multiple framebuffer resolutions
-- Fullscreen/borderless/windowed modes


==============================================================
What doesn't work
==============================================================
-- Online play
-- Screenshots
-- 64 bit versions (only 32 bit code compiles at the moment)
(Insert some other features that I probably overlooked)


==============================================================
Supported platforms/OS's
==============================================================
-- Linux (32 bit binary).
-- Windows 7 (32 bit binary). I'm sure other Windows versions work as well, but I don't have them installed to confirm.


==============================================================
Dependecies
==============================================================
-- SDL2
-- SDL2_mixer
-- OpenGL 2.1 (optional)


==============================================================
Misc notes
==============================================================
As mentioned in the dependencies, I used SDL2 for pretty much everything that invovles input, audio, and video.
This means that you only depend on having SDL2/SDL2_mixer to compile the entire game.

That said, I added an (optional) additional rendering backend that uses OpenGL and GLSL
to render the palette in a shader. This saves having to convert the framebuffer
to a 32bit texture on the CPU, which is a nice performance gain when you are using a higher resolution framebuffer.

==============================================================
Regarding the release of this port
==============================================================
As of 2023 August, the code is pretty much ready for release, save for a few minor tweaks.
Right now the biggest issue is installation/compiling on other users' machines.
It is not user friendly in any capacity.
Linux users can probably use the default Makefile, which assumes all dependencies are installed.
Windows builds are currently cross-compiled with MinGW. I haven't worked on a 'cl' compatible build yet.
I'm also testing out the Meson build system, which does solve a few things regarding distribution, 
but being a relatively new build system it may not always be installed.

Mac ports will require someone additional help, since I don't own a mac, or have ever developed on one.
Hopefully it's not too difficult to add support for this.

A binary release may be possible if players are okay with using pre-compiled binaries.


==============================================================
Thanks
==============================================================
id Software
QuakeSpasm Developers
SDL Developers
The thousands of Quake players, mappers, modders, and developers that keep the game alive


-- SoftQuake developer
   2023 August
