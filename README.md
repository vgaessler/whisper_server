#Whisper OpenSim Voice Module#

For detailed documentation please check [CONFIG].

#Building#

To use Whisper, one has to

1.  Build and/or install the OpenSimulator module.
2.  Build and/or install the Murmur viewer executable (which currently replaces SLVoice.exe in the viewer)
3.  Run a murmur server to route voice data between viewers after channels have been established via the
OpenSimulator module.

For detailed instructions on 2 and 3, please see [CONFIG].  Here, we will describe the process of building and 
configuring the OpenSimulator module in a bit more detail.

##Building the OpenSimulator module##

1.  Copy this directory to $OPENSIM_BASE/addon-modules/Whisper
2.  Follow the instructions at [MODULE BUILD] to build the module.  This will copy the generated DLL automatically
into your $OPENSIM_BASE/bin directory.

##Installing the OpenSimulator module##

Alternatively, you can install the prebuilt bin/Whisper.dll into $OPENSIM_BASE/bin.  This was built under
Mono but should work on other systems.  You will also need to copy over bin/Ice.dll and bin/Glacier2.dll if you 
are going to use the Glacier option.

## Configuring the module##

1.  Copy the contents of the OpenSim.ini.include file into your OpenSim.ini

#References#

[CONFIG] - doc/Whisper_Murmur_Config.pdf
[MODULE BUILD] - http://opensimulator.org/wiki/IRegionModule#Building_Region_Modules

#Release Notes#

##Development##
- updated to compile from OpenSim 0.7.3 to 0.8 and current OpenSimulator dev code.

##0.2.0##
- updated to compile for OpenSim 0.7.1+ (thanks to Justin)
- grid support (thanks Snoopy)
- glacier2 support (thanks Brian)

##0.1.0##
- initial version
- for OpenSim standalone configuration

#Credits#
* Volker Gaessler (vcomm.ch)
* Snoopy Pfeffer (dreamlandmetaverse.com)
* Justin Clark-Casey (justincc.org)
* Brian Becker
