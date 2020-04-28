
                               Game Launcher
                                      
                        Version 0.9.8 - 14 May 2002
                         (C) 1999-2002, Dave Dribin
   
What Is It

   Game Launcher is a cross platform universal front end for emulators.
   The main goal is to provide a user interface that is easy to use and
   attractive, yet does not look like a tradition user interface with
   windows and such. Game Launcher should work with any emulator. It has
   been known to work with MAME, Nesticle, RockNES, zSNES, snes9x,
   Callus, Stella, z26, and Genecyst. Game Launcher has been ported to
   DOS, Windows, and Unix.
   
Who and Why

   Game Launcher was written by Dave Dribin. I wrote it because I wanted
   something a little different than existing DOS front ends. It is
   intended for people using VGA monitors (including the Wells-Gardner
   U3100 SVGA monitor) inside an arcade cabinet. The latest version can
   always be found at http://www.dribin.org/dave/game_launcher/.
   
   Please do not email me support questions directly. Subscribe to the
   glaunch-public mailing list and send support questions there. See the
   Game Launcher web site for subscription information.
   
Features

     * Very flexible. It should run with any command line based emulator.
     * Simple and easy to use interface.
     * Customizable screen resolution.
     * Customizable font.
     * Supports rotated monitors.
     * Plays music in the background (MP3s or an audio CD).
     * Displays screen shots (PNG, PCX, BMP, and JPEG).
     * Slight menu animations.
     * Support for PC joysticks.
       
Configuring Game Launcher

   The glaunch.cfg file contains the global configuration options. It
   contains a list of emulators to support and what kind of background
   music is desired. All other configuration options are emulator
   specific and are contained in the config/ directory.
   
   Each emulator listed in glaunch.cfg must have a corresponding cfg file
   in the config/ directory. For example, if "mame" is listed in
   glaunch.cfg, then config/mame.cfg contains the configuration options
   for MAME.
   
   I will beef up this section more later, but for now, please look at
   config/template.cfg and the other examples I use provided in the
   config/ directory. I've tried to make the config file
   self-documenting. :)
   
  Using mamescan.exe
  
   mamescan.exe is a command line tool that automatically creates a .map
   and .rom file for MAME by scanning the ROMs you have installed. It
   uses the MAME executable to figure out which ROMs are buried inside
   merged ROMs. By default, only the primary ROMs are included and all
   clones are skipped. Individual ROMs may be included and excluded by
   using a constraint file.
   
   A mamescan config file, by default mamescan.cfg specifies the path the
   a MAME executable, the path to MAME ROMs, and the configuration file
   to use for Game Launcher. The configuration file to use is really the
   base pathname of the configuration file to use. Two configuration
   files are created by mamescan. If the base path name given is
   config/mame, then the files created are config/mame.map and
   config/mame.rom. This path may be relative or absolute.
   
   You can force the inclusion and exclusion of individual ROMs in the
   configuration file if you want to override the default choices. In the
   constraint section of the config file, any line beginning with a '+'
   forces inclusion and any line beginning with a '-' forces exclusion.
   For example, the pacman.zip file contains the games pacman (the Namco
   version) and pacmanm (the Midway version). The "primary" ROM is pacman
   and the clone is pacmanm, so mamescan will include pacman and exclude
   pacmanm. Say you do not want to include pacman, but want to include
   pacmanm. You can add the following lines to the constraint section of
   the configuration file:
-pacman
+pacmanm

  Configuring Screen Resolution
  
   Any resolution available by your DOS VESA driver should be available
   to use. If the chosen resolution is not available, Game Launcher will
   not run. Not all resolutions look that good, though, especially
   depending on the menu orientation. For horizontal orientation, I would
   recommend either 800x600 or 400x300. 800x600 looks much nicer because
   the anti-aliasing of the fonts is much less noticeable. For vertical
   orientation, I would recommend either 640x480 or 320x240. 640x480
   looks nicer again because of the anti-aliasing.
   
   Also higher resolutions may result in slower animations. This can be
   caused by running out of VRAM or processing power. The lack of VRAM
   causes slower animation because Game Launcher will use VRAM if your
   video card supports hardware acceleration. If you're curious if VRAM
   is being used, check the log file. If your video driver does not
   support hardware acceleration, then VRAM will not be used under any
   circumstances.
   
  Configuring Fonts
  
   Any TrueType font is supported, although very thin and/or small fonts
   may show some pink spots. The font size is fully customizable by
   choosing the point size. An appropriate size is mostly personal
   preference. I prefer an 18 point font in horizontal orientation at a
   resolution of 800x600 or vertical orientation at 640x480, but smaller
   fonts look OK, too. For smaller resolutions, I prefer a 10 point font
   for horizontal orientation at 400x300 or vertical orientation at
   320x240. You really cannot go any smaller than 8 point without the
   font looking terrible. Any larger than 10 point results in only a few
   menu items to fit on the screen. 10 points seems like a nice
   compromise.
   
  Configuring Screen Shots
  
   The first configuration parameter of the screen shot is the delay to
   wait before displaying the screen shot. This helps speed up the
   scrolling by not displaying every screen shot right away. Of course
   you can make this as low as you want (even zero) if you like.
   
   The brightness of the screen shot is also configurable. If the screen
   shot is too bright, then the menu text is hard to read. If the screen
   shot is too dim, then it can barely be seen. Tweak this parameter to
   your tastes.
   
   Finally, how the screen shot is scaled is also configurable. The
   screen shot is always scaled to the largest possible size, otherwise
   it could be very tiny. Since screen shots are rarely an exact multiple
   of the screen resolution, the scaling factor of the screen shot may be
   non-integer number. When a screen shot is scaled by a non-integer, it
   will get distorted. Because I don't like the distortion, there is an
   option to prefer integer scaling factors over non-integer factors. If
   the screen shot needs to be shrunk, then non-integer scaling factors
   will be used since distortion is bound to happen anyways. If the
   distortion doesn't bother you, then turn of integer scaling all the
   time. You will get screen shots with a better fit at the cost of
   distortion. The choice is up to you.
   
  Key Mappings
  
   The following table summarizes the default key mapping:
   
   UP, DOWN Move the game selection up/down one game.
   RIGHT, LEFT Move the game selection up/down one screen, like page up
   and page down.
   1 Play selected game.
   LEFT CONTROL Go to next emulator.
   LEFT ALT Go to previous emulator.
   ESC Exit Game Launcher.
   SPACE Displays the screen shot. Press again to get back to menu.
   G Skip to next MP3.
   D Restart current MP3.
   
   All key mappings are configurable in glaunch.cfg.
   
  Launching Arbitrary Programs
  
   Emulators are not the only program that Game Launcher can run. Any
   arbitrary program can be launched. I've included one technique to do
   this with the "Misc" menu. The "Misc" menu scans the /misc/ directory
   for any batch files. These batch files are added to the menu and run
   when launched. You can create batch files to launch any command line
   program. I have used this to run Doom, Quake, and the QuickView video
   program. Please see the misc.cfg and misc.map files for more
   information.
   
Running Game Launcher

   After configuring Game Launcher, type "glaunch" to run it. There are
   no command line options. If the configuration is setup correctly, you
   will get a list of games to choose from. You may move up or down one
   game at a time or one page at a time. You may also switch emulators in
   which case a new selection of games will be presented. A small icon
   will appear to the right of the names of games that have a screen shot
   available. The icon may be turned off in the global configuration
   file.
   
  Troubleshooting
  
   There are a number of avenues to pursue if you have problems getting
   Game Launcher to do what you want. The first thing you should do is
   turn on debug mode by changing the debug parameter in glaunch.cfg.
   This allows you to see exactly what commands are being run and the
   output of the commands. It is invaluable to help you narrow down
   configuration issues.
   
   A number of log files are also generated in the log/ directory. The
   glaunch.log file contains various information and error messages. You
   may sometimes find helpful information in here when things go wrong.
   The runit.log file contains the output of the last emulator launched.
   If an emulator does not run as expected, an error message may be
   available in this file. Both of these log files are rotated so that
   the 6 newest copies are kept around.
   
   If you still are having problems, join the glaunch-public mailing list
   and ask questions there. Always provide as much information as
   possible when soliciting help, such as which version of Game Launcher
   you are using, which operating system you are using, and anything else
   that may be pertinent (sound cards, video cards, etc.). Attaching the
   glaunch.log file can also provide good background information to
   people willing to help. For information on how to subscribe to the
   mailing list, please see the Game Launcher web site.
   
  The State File
  
   The file glaunch.sta contains state information that needs to be
   preserved between invocations. Do not edit this file as the data is
   internal to Game Launcher. You may safely delete this file without
   affecting any of your configuration files.
   
Compiling

   The Game Launcher source code is released under the GNU General Public
   License. In interest of reuse, it requires a number of tools and
   libraries in order to compile. All of them are freely available.
   
   Tools for DOS:
   
     * DJGPP v2.x: A GCC port to DOS. Do not use GCC 3.x as there are
       still a number of bugs.
     * Various GNU tools ported to DOS (make, fileutils).
     * NASM (Netwide Assembler) v0.98+: A 16-bit assembler.
     * VAL: A 16-bit linker.
     * UPX: An executable compressor.
     * Lynx: A DOS port of the text only browser. It is used to convert
       HTML files to text files.
       
   Tools for Windows:
   
     * MinGW: A GCC port to Windows.
     * Cygwin: Unix utilities ported to Windows. You will need the
       fileutils, lynx, and upx packages. Do not get GCC or binutils!
       
   Tools for Unix:
   
     * GCC: Theu GNU C/C++ compiler.
     * Lynx: A text only browser.
       
   Libraries needed:
   
     * Allegro 4.0.x: A multi-platform graphics programming library.
     * loadpng v0.9+: A PNG extension to Allegro, requires libpng and
       Allegro.
     * AllegroMP3 v1.6+: An MP3 library, requires Allegro.
     * libbcd: A library to interface to MSCDEX, the CD driver (DOS
       only).
     * libpng: A portable PNG library, requires zlib.
     * zlib: A portable compression library.
     * AllegTTF v2.0+: A TrueType font renderer for Allegro. It includes
       code from the FreeType project.
     * JPGAlleg v1.1: A JPEG loader for Allegro.
     * jpgal11b.zip: A patch to JPGAlleg v1.1 for modifications needed
       specifically for Game Launcher.
       
   Once you have all the tools and libraries installed, unzip the source
   code, edit common.mk to match your system, and type "make". If you
   plan on doing any real development, you should run "make depend" first
   to give you accurate dependency checking.
