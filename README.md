NodeWebba
=========

Create Generative Music with Variable-Coupled Map Networks

Bret Battey / Bat Hat Media

Nodewebba is generative music software in which a web of feedback-based pattern generators creates dynamic, interlocking melodic and rhythmic patterns. It brings my concept of Variable-Coupled Map Networks (VCMN) out of the research lab and into the home studio.

I created Nodewebba using Cycling74's Max 7. 

See http://BatHatMedia.com/software/nodewebba/ for downloadable binaries, video overviews, installation instructions and other user documentation.


Versions
==================

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
