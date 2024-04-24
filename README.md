OpenBMC power supply firmware

This directory contains P11 power supply firmware images supplied by the
vendors. Each PSU firmware should reside in a directory named as the PSU CCIN.
The firmware image file prefix should be replaced with IBM PSU CCIN and postfix
must remain as is. The PSU CCIN dir should contains the firmware file and
MANIFEST file. The contents of CCIN dir can be generated in 2 ways:

* - Use tool to Generate Tarball with PSU image and MANIFEST Script, the
    tool located at phosphor-psu-code-mgmt/tools/generate-psu-tar then extract
    the tarball into the PSU CCIN dir.
OR 

* - Add firmware file to PSU CCIN Dir and create file with the following
    contents:
    purpose=xyz.openbmc_project.Software.Version.VersionPurpose.PSU
    version=003000390031
    extended_version=model=2B1E,manufacturer=

Note: Files don't exist in this directory will require addition in
      openbmc/meta-phosphor/recipes-phosphor/power/device-images.bb

