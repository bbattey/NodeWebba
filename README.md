NodeWebba
=========

Create Generative Music with Variable-Coupled Map Networks

Bret Battey / Bat Hat Media

Nodewebba is generative music software in which a web of feedback-based pattern generators creates dynamic, interlocking melodic and rhythmic patterns. It brings my concept of Variable-Coupled Map Networks (VCMN) out of the research lab and into the home studio.

I created Nodewebba using Cycling74's Max. 

See http://BatHatMedia.com/software/nodewebba/ for downloadable binaries, video overviews, installation instructions and other user documentation.


Versions
==================

v0.101    (Sep 16, 2020)
==================

New Features
--------
* Reconfigured the Node-preset file-save mechanism so it automatically keep 1 backup version (with .bak in the filename) if user overwrites the same filename, to help reduce risk of accidental loss/overwrite. (Unfortunately, this option is not available in Max for the presets controlling the matrix.)


v0.10    (Feb 26, 2020)
==================

New Features
--------
* MAJOR CHANGE: now using integer rather than float values for a, b and m, and m is variable rather than  operating at a fixed 1.0. This is in keeping with the original Lehmer's Linear Congruence Formula. It is also necessary to ensure consistent results, since floating point operations can introduce unpredictabilities. Providing variable M also provides more control over the patterning of a node.

* The MIDI device menu settings are now stored in presets by name rather than by position on list, so, in
    theory, you should could the correct device even if the order of items in the list differs.

Note that the above changes will break presets made in previous versions

* aout, bout and mout node output variables are sent whenever a, b or m are changed (facilitates
     having an extral controller display the state of a node)

* adirect and bdirect node input variables allow direct setting of a and b integer values rather than
     having to send a 0-1 scalar.

* Duration is now calculated based on a minimum rhythm unit of 1 rather than the node's minimum rhythm unit. This will help ensure one can get durations shorter than the inter-onset rhythm. 

Fixes
-----
* Given the same startup configuration and reseeding, should always provide the same behaviour.
* Resolved input-variable name class between m and mode selection
* In the node box GUI, rhythm and dur have been set to be non-editable


Other
-----
* Significant redesign under the hood to simplify/clarify the system logic
* Added node output-state variables for node on/off and mute on/off


v0.06    (Jan 3, 2018)
==================

* Rebuild in Max 8.0.2


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
