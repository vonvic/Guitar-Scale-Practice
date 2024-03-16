# Guitar Scale Practice
This project provides a guitarist exercises to better their navigation around the freboard.

In contrast to the piano, like many stringed instruments, it has a weird, segmented visualization of scales. The piano visualizes sheet music in a one-to-one correspondence. Meaning, notes only travel one direction:
 - Left to right for the piano 
 - Bottom to top for sheet music

No notes repeat...

With the guitar, however, notes DO repeat. With standard tuning EADGBe, the 5th fret at the low E string is the same note as the open A string. This is occurs with all the other strings, except for the G string and the B string, where the *4th* fret of the 3rd string is identical to the open 2nd string. While it seems like this redundancy is unnecessary, this actually allows for a chords of wider range. The notes are placed **left to right** AND **bottom to top**. 

## Background Research
The [Piano-ologist](https://www.youtube.com/@Pianoologist) YouTuber released a video that better helped me understand music better as whole. This video is [Solfege Recognition: An Ear Training Idea](https://www.youtube.com/watch?v=JWxUcT7ekCo&ab_channel=Piano-ologist). 

The idea is to recognize a note by its function in a scale. In the video, he establishes the major scale through a V7 - I resolution, before then playing a random note for us to guess.

## High-Level Features
### V0.1 Major Scale Familiarization

This version will focus on just familiarizing the guitarist with the major scale positions. There will be 7 positions, with each representing modes of the major scale. In each position, each string will have three notes played.

Logic goes like this:
```text
Position will be specified first.
Solfege number will be requested to play.
The user will press SPACEBAR to continue, or any other key to exit.
```

There will be no validation present. Instead, the guitarist will self-verify that they played the right note.

**Example run through**
```text
Position: 1st position
Play the 5th note (So) of the scale...
Press SPACEBAR to continue, or any other key to exit 
```

#### Implementation Details

##### Program Initialization
The program will load the scale positions from text files. They will be placed in the `data/positions/` directory, with filenames `n.txt`, where n is the position number (e.g. `1.txt`, `2.txt`, etc.). Each file be formatted as such:
```text
6: note1 note2 note3
5: note1 note2 note3
.
.
.
1: note1 note2 note3
```
where `note1`, `note2`, and `note3` represent the note number in the scale.

For example, for 1.txt:
```text
6: 1 2 3
5: 4 5 6
4: 7 1 2
3: 3 4 5
2: 6 7 1
1: 2 3 4
```

##### Runtime Behavior
Program will start immediately, specifying the position number, as well as the note requested.