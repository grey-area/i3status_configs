I had some requests for my i3 status bar config files. Here they are.

(Note, I'm mostly just using py3status and pre-existing modules for it.)

![](status_bar.png)

From left to right the bar has:

- clickable elements that switch between single display, dual display, and mirrored display;
- clickable elements for lauching a settings GUI or taking a screenshot;
- a pomodoro timer that cycles between inactive/pomodoro/break state when clicked, and triggers a pop-up message when the timer expires;
- what's currently playing on Spotify, if anything;
- current audio volume;
- current battery state;
- current date and time;
- bluetooth; and
- a networking applet menu.

Also note that the font isn't the usual horrible i3status font.

Installation
============

Since the requests came from i3 users, I'll assume you already have i3 installed.

1. Install py3status (e.g. sudo apt install py3status)
2. Put the files from the i3_configs directory in ~/.i3. These are an i3 config file and a py3status config file. If you already have an i3 config that you don't want to overwrite, just copy in the bar{...} block.
3. If you want the display switching functionality, put the files from the scripts directory somewhere that's in your path, make sure you have xrandr installed, and change the display names referred to in those scripts (running xrandr will tell you the names of displays that are available).
4. If you want the screenshot functionality you'll need scrot (installable via apt). If you want to use something else, modify the screenshot{...} block of the i3status.conf file.
5. The settings element is set up to launch mate-control-center when clicked, which is a nice lightweight settings GUI (installable via apt). If you want this to launch something else then edit the control{...} block of the i3status.conf file.
6. You may need to install the pytz and tzlocal python packages in order for the clock to work.

Of course, to see the changes you'll need to reload i3 via whatever shortcut you have setup for that, or with 'i3-msg reload' at the command line.
