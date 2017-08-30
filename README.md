# OpenVPN_30.08.2017
Integration of OpenVPN-2.4.x into IPFire environment, includes also bufixes from current Bugzilla.

Feature list:
All new features will now be integrated into one dev version. The "Minimal solution" will be skippt but only be marked in this README file.


Included source versions are:

OpenVPN-2.4.3 ; lz4-1.7.5

Language Files are from Core 111

---------------------------------------------------------------------------------------------------------------

Minimal version:

The "minimum version" contains needed changes in ovpnmain.cgi to bring OpenVPN-2.4.x to live on IPFire. The changes contains the following:

- Global (global WUI section) and client specific (CCD section) selection for the cipher negotitation via a checkbox named "Automatic cipher negotiation:". This option is set automatically on OpenVPN side. To prevent this new feature and stay in IPFires old configuration format the directive are deactivated (no hock in the checkbox) and "--disbable-ncp' will be set in server.conf.
. Since OpenVPN-2.4.x OpenVPN do NOT accept the 'script-security 3 system' directive causing security concerns. This directive has been changed to 'script-security 3' .


---------------------------------------------------------------------------------------------------------------

Extended version:


The "extended version" contains all above mentioned minimum changes but also new features in ovpnmain.cgi. The changes contains the following:

- New GCM cipher, for Roadwarrior and N2N (for AES-128, 192 and 256 Bit) which are in the cipher menu available .
- Sorted algorithm lists with description (with weak, medium and strong algorithms) for ciphers, HMACs and DH-parameter (causes also the sweet32 thing).
- New menu for key lenghts for the ROOT (6144, 8192, 12288 bit) and HOST (4096, 6144, 8192, 12288 bit) and HOST CA which is available while a new PKI will be generated.
- "--tls-crypt" has been introduced for N2N section.
- LZ4-v2 compression for Roadwarrior in CCD section (pushable directive, changes in client.ovpnÂ´s are not needed) has been added in here --> https://forum.ipfire.org/viewtopic.php?f=50&t=18067#p104629 .
- LZ4-v2 has also been added for N2N connections --> https://forum.ipfire.org/viewtopic.php?f=50&t=18067&start=15#p106499 .


Bug fixes from IPFire´s Bugzilla entries:

- https://bugzilla.ipfire.org/show_bug.cgi?id=11364
- https://bugzilla.ipfire.org/show_bug.cgi?id=11307
- https://bugzilla.ipfire.org/show_bug.cgi?id=10482
- https://bugzilla.ipfire.org/show_bug.cgi?id=11424

