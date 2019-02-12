NodeWebba
=========

Create Generative Music with Variable-Coupled Map Networks

Bret Battey / Bat Hat Media

Nodewebba is generative music software in which a web of feedback-based pattern generators creates dynamic, interlocking melodic and rhythmic patterns. It brings my concept of Variable-Coupled Map Networks (VCMN) out of the research lab and into the home studio.

I created Nodewebba using Cycling74's Max. 

See http://BatHatMedia.com/software/nodewebba/ for downloadable binaries, video overviews, installation instructions and other user documentation.


Versions
==================

v0.07    (Jan 3, 2018)
==================

New Features
--------
* Can now specify the base rhythm unit (rather than being stuck with 16ths), and can set a different rhythm unit for each node
* When working with Max, can now specify a custom scale/mode via the custMode global (see Coder's Reference)
* Changed how mapping to a scale/mode is handled. Now one can simply indicate a highest and lowest allowed note, provide a tonic note to build the mode from, then use a scalar between 0 and 1 to determine which portion of that maximum play range is actually used. 
* Gated hostsync~ data so one can turn on the audio system w/o effecting the nodewebba transport

Fixes
-----
* The external-variable input to control instrument range was not connected correctly

Issues
------
* The variable base-rhythm unit implementation has (re)introduced a bug where the same re-seeded node-configuration startup setup does not always produce the same results.

v0.06    (Jan 3, 2018)
==================

* Updated to Max 8.0.2



v0.05    (Sep 5, 2016)
==================

New Features
--------
* Hours/Minutes/Seconds display
* MIDI control presets separated from the main/node presets


Fixes
-----
* Fixed reseed (broken in 0.04)
* Fixed situation where first two notes sometimes jammed together when turning on main transport
* Fixed occasional inconsistencies in startup; now a reseeded preset should reproduce the same behaviour each time

Other
-----
* Core imap object is now two state: when receives a seed, will output that seed on the next bang, then will iterate prior to output after that point
* Separated update, firing, and rhythm/duration/MIDI output stages to provide more consistent/intuitive links between node outputs, state, and rhythm/duration
* Set preset save mode to trigger a save dialog if presets have changed and the user leaves the program (previously just wrote out the changes immediately)
* Slightly clearer default file name for presets files
* A few ticks are shaved off the duration to ensure that when rhyhtm = duration that the duration is slightly less than the rhythm -- so synths that won't allow overlapped repeated notes are more likely to work 


v0.04    (Mar 18, 2016)
==================

New Features
--------
* ReWire Sync to external sequencer
* Bars/Beats/Ticks display

Fixes
-----
* MIDI device names now stored with presets, rather than device-menu item number (so device should restore correctly even if the system MIDI configuration changes)
* MIDI device refresh refreshes the list in the interface for each node, as well as the MIDI controllers interface.
* wrapping of node state corrected: returns 0 rather than 1 when given a -1
* changed selected-preset color to be more visible
* help text for 'controller learned' light in MIDI Control window corrected




v0.03
==================

Fixes
-----
* User interface window should now appear consistently


v0.02b
==================

Fixes
-----
* recompiled for MacOS El Capitan


v0.02
==================

Fixes
-----
* tempo no longer reverts to 120 bpm when play is enabled
* added user-control of humanisation functions
* main play button now triggers reseed for nodes
* minor GUI adjustments


v0.011
==================
First public version
