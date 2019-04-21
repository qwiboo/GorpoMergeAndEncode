# GorpoMergeAndEncode
Merge and encode single videos split in multiple mp4 files with Powershell using **MKVToolNix and Handbrake**

## Description
Merge and encode single videos split in multiple mp4 files in the given gopro export folder and removes original files if succesfull.
It can handle mulitple single videos in the same directory.
Requires [MKVmerge](https://mkvtoolnix.download/) and [HandBrakeCLI](https://handbrake.fr/downloads2.php) installed in C:/Program Files/MKVToolNix\ and C:\Program Files\HandBrake\ respectively.


See [official Handbrake presets](https://handbrake.fr/docs/en/latest/technical/official-presets.html)

Output file is Encoded-{original filename}-{date of subfolder}

## Parameters

* -dir Defaults to current directory
* -preset Default preset "Vimeo YouTube HQ 1440p60 2.5K"
* -MKVMergeExtraParam Extra parameters for MKVMerge
* -HandbrakeExtraParam Extra parameters for Handbrake
* -test Test merge and encode three seconds of each video, without deleting the original files
* -delete Delete original files if not error is returned. Defaults to true
* -mergeAll Ignore file naming and merge all files in the directory
* -noEncoding Skip encoding step


## Example
**.\goproMergeEncode1440p60.ps1 -dir "d:\Video\GoPro\2019-04-21\HERO5 Black 1\" -preset "Vimeo YouTube HQ 1440p60 2.5K"**
Output file for D:\Video\GoPro\2019-04-21\HERO5 Black 1\GOPR2548.MP4 is Encoded-GOPR2548-20190421.mp4

## Notes
Based on the file name format GOPR2548.MP4 and multiple files GP012548.MP4, GP022548.MP4,... and folder structure ..\GoPro\2019-04-21\HERO5 Black 1\
Note that the stucture works for single videos for the camera models: HD HERO2, HERO3, HERO3+, HERO (2014), HERO Session, HERO4, HERO5 Black, HERO5 Session, HERO (2018)

For HERO6 Black, & HERO7 (White, Silver, Black) or other formats use -mergeAll parameter
See [GoPro Camera File Naming Convention](https://gopro.com/help/articles/question_answer/GoPro-Camera-File-Naming-Convention)
