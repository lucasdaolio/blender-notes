# Video Editor

## In summary

Work by strip, encode, for loops, use filter and groups

In need to repeat, use filter/groups, mark the item of everything and limit the lengh and quality of video/audio by the biggest one

## Settings

Default format: 720p, 30fps, H.264(mpeg-4), aac(128kbs),512mb.\
Lossless: FFV1 codec, PCM Audio.\
Lossless ignores bitrate.\
**S**/**E** in Timeline Editor: Start/End frame.\
Backspace in a timeline gap: remove gap
**Page up**/**down**: Skip to Start/End of the strip.\
**P**: Preview limit.\
**X**: Delete.

## Workflow

In Video sequence Editor, check Show Offsets and in Timeline Editor check Audio Scrubbing, Frame Syncinc and Frame dropping.\
Select a video and LMB Video Sequence Editor > Set Render Size.\
Home select all visible objects.\
Always hide videos with filter.\
Videos with different frame rates Can be sync using the calculation: Wanted FPS/Video FPS = Speed Filter Value.\
Use the same % of video proxy make the preview run on the same.\
Mpeg preseek store all frames before run the playback.\
For "Fade-in/out", Add a color, and select the A strip, then the B Strip, the add Gamma Cross Filter.\
Use "Cross-fade audio" to make audio transition.\
GOP = FPS/2.\
Audio config. Is in Render Tab.\
To join 3D Scene with video, set Render Tab > Shading > Alpha = Transparency.

Never put Audio strip in na group with effect.

To change video speed, cut the wanted part and set the speed factor on video because audio does not follow the changes\
In UV Editor > Mask Mode, check Match Movie Leght and Auto Refresh properties\
Ctrl-LMB: Apply mask point
