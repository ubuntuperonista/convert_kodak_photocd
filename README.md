# convert_kodak_photocd

Bulk Kodak PhotoCD Image Converter for Linux.

Requires Wine and kmaragos's pcdtojpeg.exe utility.

## In Ubuntu/Debian:

Install the dependencies.

<code>
sudo apt install git wine mdf2iso ccd2iso
</code>

Prepare pcdtojpeg.exe to work on Linux:

<code>
cd /tmp ;
git clone https://github.com/kmaragos/pcdtojpeg
sudo mkdir /opt/pcdtojpeg/ ;
sudo cp /tmp/pcdtojpeg/Binaries/Windows/pcdtojpeg.exe /opt/pcdtojpeg/
</code>

## Convert the Kodak PhotoCD disk image into a standard ISO image:

### If your Kodak PhotoCD is a BIN/CUE image

<code>
ccd2usi PCDmmyy.bin
PCDmmyy.cue
</code>

You will get a PCDmmyy.iso CD-ROM image.

### If your Kodak PhotoCD is a MDF/MFS image

<code>
mdf2iso --cue PCDmmyy.mdf
ccd2iso PCDmmyy.bin
</code>

You will get a PCDmmyy.iso CD-ROM image.

## Bulk convert every PCD file from PCDmmyy.iso CD-ROM image:

Mount the .iso file.

<code>
cd PHOTO_CD/IMAGE/ ;
./convert_PCDs.sh
</code>
