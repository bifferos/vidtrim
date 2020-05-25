Simple video cutting, needing only mplayer, ffmpeg and python3.

1) Run vidtrim <video file>.  This will start mplayer playing
   your video.

2) Navigate to the start of your clip using a combination of the 
   arrow keys, space bar or dot to go forward frame by frame and
   pause the video.  (See mplayer man page for further details)

3) Press the 'i' key to set the start of the saved video clip

4) Navigate to the end of the clip you want to save.

5) Press the 'i' key again to mark the end of the clip.

6) Press the 'q' button to quit mplayer, your video clip will be
   extracted and named as:

   <originalfile>_c<NN>.<originalextension>
   So if you had file.mp4 the clip would be called file_c00.mp4

7) Now you will see the newly created clip playing in mplayer.
   It will play in a loop an infinite number of times so you can 
   check it's how you want it.  Note that the resulting lead-in 
   and lead-out points can get adjusted by ffmpeg according to 
   the position of i-frames, so this check is important.

8) If you like what you see, just press 'q' at this point to 
   keep the clip.

9) If you made a mistake just hit 'i' before pressing 'q' and 
   vidtrim will delete the file it just created, saving you the
   trouble.

Note that vidtrim creates the file ~/.vidtrim_trimfile.txt to store
the timecodes, it will overwrite this file if it already exists.

Optional -s and -f arguments cause vidtrim to move the lead-in or
lead-out respectively to the start or end of file.  You still have
to press the 'i' key twice when supplying these arguments because 
mplayer expects two presses or won't write any timecodes at all.

You can specify both -s and -f but it makes little sense as it will
just then ignore both presses of the 'i' key and copy the whole
video.
