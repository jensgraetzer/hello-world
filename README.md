# MP3-ID3v2-Frames-Remixing

Creators of new content ideas, involving the ID3v2 tag of MP3 files, need to create content prototypes. The Python scripts of this project may support this experimental content creation. There is a Python script, that exports parts such as the frames of a ID3v2 tag and the audio itself into separate files. Every frame of the ID3V2 tag will be stored in a single file. These files can be edited. Some of the frame files can be deleted. Or a newly created frame files can be added. There is another Python script, that reassembles these files into a new version of the MP3 file.

# id3v2TagExtractor.py

This Python script takes a MP3 file with a ID3v2.4 tag and ceates a number of new files. It creates a file with the pure audio data. This audio file has the file name XXX_audio.mp3.

And it creates files for every ID3v2 frame found. The names of these files are XXX_N*.bin, where * is a number plus the name of a ID3v2 frame. The number defines the position of the frame within the ID3v2 tag.

Usage: Run the script id3v2TagExtractor.py. A file picker opens. Pick a MP3 file and press the "open" button. 

# id3v2TagReassembler.py

This Python script takes the XXX_audio.mp3 file and all the frames binary files and creates a new MP3 file from it. The new audio file has the file name XXX_newAudio.mp3. It has a ID3v2.4 tag.

# id3v2FrameCreator_APIC.py

This Python script creates the binary of an APIC frame, containing a picture. The binary is stored in the file with the name XXX_N999_APIC.bin. Adding this binary file to other binary files, than run the id3v2TagReassembler.py script, creates a MP3 file with a picture.

# id3v2FrameCreator_XSRT.py

This Python script creates the binary of an experimental frame called XSRT. This frame contains SRT subtitles. The frame has a format similar to the USLT frame. The Python script reads a text file with the SRT data and stores it in a file with the name XXX_N999_XSRT.bin.

# id3v2TagFramesSizeCheck.py

This Python script checks the frame size value, found in the frame binary files XXX_N*.bin. It tells, wether the value is stored as a synchsave integer value or not. The standard ID3v2.4 requires a synchsave integer value. But the standard ID3v2.3 requires a standard integer value. So, mind the tag version!
