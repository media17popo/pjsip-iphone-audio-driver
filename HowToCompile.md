# Introduction #

In order to provide precise step-by-step build instructions, we've opted to write these instructions to target a specific version of PJSIP. We recommend you follow these instructions to the letter first (so you have a working build) before venturing off to another version of PJSIP.

# Step 0 #

These instructions have been tested with the iPhone SDK 3.1.2 on:
  * Leopard 10.5.8
  * Snow Leopard 10.6.2

# Step 1 #

Download PJSIP v1.0.3 from subversion. Open up your terminal, and execute the following 2 commands:

  * `cd ~/Desktop`
  * `svn checkout http://svn.pjsip.org/repos/pjproject/tags/1.0.3 pjsip`

This will create a folder called "pjsip" on your Desktop, and download the PJSIP 1.0.3 release into that folder. The rest of the instructions assume the folder is on your Desktop.

# Step 2 #

Download the latest version of the iPhone audio driver from the Downloads page.

Then place the downloaded audio driver file into the location:<br />
`~/Desktop/pjsip/pjmedia/src/pjmedia/iphonesound.c`

# Step 3 #

Download the pjsip-patch-1\_0\_3.txt from the Downloads page.<br />
Then place the downloaded patch file on your Desktop.

# Step 4 #

Apply the patch file by executing the following two commands:

  * `cd ~/Desktop/pjsip`
  * `patch -p1 < ../pjsip-patch-1_0_3.txt`

# Step 5 #

Compile pjsip by executing the following 3 commands:

  * `cd ~/Desktop/pjsip`
  * `chmod 755 compile.sh`
  * `./compile.sh`

After several minutes, the pjsip libraries will be compiled.  You can find the library files here:

  * pjlib/lib/libpj-arm-apple-darwin9.a
  * pjlib-util/lib/libpjlib-util-arm-apple-darwin9.a
  * pjmedia/lib/libpjmedia-arm-apple-darwin9.a
  * pjmedia/lib/libpjmedia-codec-arm-apple-darwin9.a
  * pjmedia/lib/libpjsdp-arm-apple-darwin9.a
  * pjnath/lib/libpjnath-arm-apple-darwin9.a
  * pjsip/lib/libpjsip-arm-apple-darwin9.a
  * pjsip/lib/libpjsip-simple-arm-apple-darwin9.a
  * pjsip/lib/libpjsip-ua-arm-apple-darwin9.a
  * pjsip/lib/libpjsua-arm-apple-darwin9.a
  * third\_party/lib/libgsmcodec-arm-apple-darwin9.a
  * third\_party/lib/libmilenage-arm-apple-darwin9.a
  * third\_party/lib/libresample-arm-apple-darwin9.a
  * third\_party/lib/libsrtp-arm-apple-darwin9.a

Compilation is now done.  Now go learn about pjsip!

# Notes #

The `compile.sh` script builds specifically with iPhone SDK 3.1.2.  To build with another version of the iPhone SDK pass in the version number as the first argument.  For example, to build with iPhone SDK 3.0 (the earliest version tested) in Step 5 use `./compile.sh 3.0`

# Thanks #
Special thanks to Samuel Vinson of the [Siphon Project](http://code.google.com/p/siphon/) for getting PJSIP to compile for the iPhone SDK and inspiring this work.

# Links #

[PJSIP Documentation](http://www.pjsip.org/docs.htm)<br />
[PJSIP Tutorial](http://trac.pjsip.org/repos/wiki/PJSIP_Tutorial)<br />
[Siphon (Example application)](http://code.google.com/p/siphon/)<br />
[Telephone (Excellent Objective-C wrappers for PJSIP)](http://code.google.com/p/telephone/)<br />