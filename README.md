OpenBMC power supply firmware

This directory contains power supply firmware images provided by vendors.
Each PSU firmware should be stored in a directory named after the PSU
model. The prefix of the firmware image file should be replaced with PSU
model, while the postfix should remain unchanged. The PSU model directory
should contain the firmware image and MANIFEST file. The contents of the
PSU model directory can be generated as follows:

* - Use the tool at phosphor-psu-code-mgmt/tools/generate-psu-tar to generate
    a tarball containing the PSU firmware image and MANIFEST file. Then extract
    the tarball into the PSU model directory.
OR 

* - Add firmware file to PSU model directory and create MANIFEST file with contents
    similar to the following:
    
    purpose=xyz.openbmc_project.Software.Version.VersionPurpose.PSU
    version=003000390031
    extended_version=model=2B1E,manufacturer=

Note: Adding new files to this repo will require change in
      openbmc/meta-phosphor/recipes-phosphor/power/device-images.bb
      to include the new FWR files into openbmc image.
