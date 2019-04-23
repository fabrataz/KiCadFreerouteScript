# KiCadFreerouteScript
Script to launch Freeroute from Kicad on MacOS (tested on Mojave with KiCad 5.1.0-0)
Slightly adapted from the work of https://forum.kicad.info/u/izzy84075 (see https://forum.kicad.info/t/freerouting-launcher/14708)
Original Source code at https://bitbucket.org/izzy84075/kicadfreeroutescript/src/master/freeroute.py?fileviewer=file-view-default

How to Use:
==========


You’ll still have to export the .dsn and import the .ses file manually, but by far the slowest part for me was getting Freerouting to actually open the .dsn file because of it’s obnoxious defaulting to the Documents folder, so this script launches FreeRouting.jar and passes it the default filename that KiCAD will pick for the .dsn, saving you possibly dozens of clicks!

Setup:
------

Place the freeroute.py file in ~/Library/Preferences/kicad/scripting/plugins

Place FreeRouting.jar (I use this version 38) in ~/Library/Preferences/kicad

In Pcbnew, under Tools -> External Plugins there should now be a Freeroute entry (If not, click the “Refresh Plugins” entry and try again).
On nightlies(Or 5.1 when it releases), you can also go into the Preferences and under Action Plugins, you can set the plugin to show directly on the toolbar.
Now, the workflow for using this:

Export DSN (File -> Export -> Specctra DSN…) using the default filename for your PCB (board.kicad_pcb would be board.dsn, for example).
Click the Freeroute button/tool entry. This should launch the usual Freeroute GUI, with your design already loaded. NOTE: The KiCAD UI might be unresponsive at this point, as it’s waiting for Freeroute to finish running.
Run your autoroute in Freeroute (Click the Autorouter button, wait, File -> Export Specctra Session File), then exit Freeroute.
Back in KiCAD, Import the session file (File -> Import -> Specctra Session…).
Done!
(This post has been mirrored into the repository at the bitbucket repository in the first link for anybody who might like to link to that instead.)

