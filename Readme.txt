Current OpenSim Revision: commit 4c1365f1496b2c60c313b6d221362d3e09a8c1d4

Instructions for Building MurmurVoice.dll:

- You need to make a link to 'opensim' which is your opensim source directory
- You must have already compiled opensim

1. cd src/
2. nant

That's it, the MurmurVoice.dll will be copied to src/opensim/bin


I had to change the ProvisionVoiceAccountRequest and
ParcelVoiceInfoRequest from what the Vivox voice module
was. This is where you will find the actual connection
details for use in the Mumble client.

This information is tentative, and subject to change.

=== ProvisionVoiceAccountRequest changes ===

What normally appears as:
http://somehost:9000/api

Has been changed to: (Used for the actual Mumble server)
tcp://murmur_hostname:MURMUR_PORT


The password for logging in should be kept as-is.

The account name is created by the following code:
"x" + Convert.ToBase64String(uuid.GetBytes()).Replace('+', '-').Replace('/', '_');

Therefore to get the UUID:
Remove the first letter x.
Replace all - with +, replace all _ with /
Convert from Base 64 string

There you have a standard 128-bit binary representation of the UUID. But I am NOT
sure what format Linden client requires it in.


=== ParcelVoiceInfoRequest changes ==

What normally appears as:
sip:SOMECHANNEL@SOMESERVER

Has been changed to:
murmur_hostname:MURMUR_PORT
