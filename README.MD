# EE Soundset Tool - A tool to easily add soundsets for the Enhanced Editions of Baldur's Gate, Baldur's Gate II, or Icewind Dale, versions 2.6 and later.

## How do I use this?

- Download this repository using the Code->Download Zip option.
- Open `cd_soundsets/english/setup.tra` and read the available options for the game. The text between the tildes is the function description summary, the text between the brackets contains the filename of the sound associated with the function. It is not necessary to utilize all entries.
- Prepare your sounds:
  - The EE games can handle PCM WAV or Ogg Vorbis (using wav extension instead of ogg) with a 8.3 filename limitation. You can use up to 6 characters for your unique soundset name with the remaining two characters being used as the function suffix.
- For each sound: Replace the function description summary with the subtitle (or leave no text between the tildes, if you don't want any). Delete and/or comment out (with placing two forward slashes at the start of the line - `//`) the functions you leave unused (don't leave them empty because the game will play silence instead).
  - Note that entry number 1070 is used on the selection soundset UI so it lacks a soundfile and it's excluded from the filename limits.
- Open `cd_soundsets/cd_soundsets.tp2` and delete/comment out the lines containing the counterpart of what you've disabled in the previous step based on the value of the index `(RESOLVE_STR_REF@INDEX)`. Also replace the `BOB` value near the end of the file with your chosen suffixless filename in full UPPERCASE.
- Distribute your converted sound files between the sounds and the wav folder, with files having a single character suffix copied to `cd_soundsets\sounds` and files having a dual character suffix copied to `cd_soundsets\wav`.
- If the language you're playing the game on is not English, replace the `en_us` country code with your own language code in line 18. You can look this up via opening the game's lang folder when in doubt.
- If you want to install multiple soundsets, duplicate everything between `LAF cd_add_soundset` through it's `END` statement in `cd_soundsets.tp2`, renumber the indexes and add these new indexes to `setup.tra` accordingly.
- Copy both the executable and the folder to your game folder and double-click on the executable.
- If you want to rename your mod so that it doesn't prompt you as "Soundset Tool", update value 0 in `setup.tpa`.

## How do I distribute my soundsets based on this?

- In order to prevent conflict with other people who would use this same template for distributing soundsets, rename everything which includes the `cd_soundsets` value to something unique. This covers the `cd_soundsets` executable and folder, the `cd_soundsets.tp2` file, and the backup folder specified in line 1 of `cd_soundsets.tp2`.
- Additionally replace the `AUTHOR` line with your contact info in line 2.

For additional support, see https://www.gibberlings3.net/forums/topic/34560-adding-soundsets-to-the-ees-using-the-ee-soundset-tool/
