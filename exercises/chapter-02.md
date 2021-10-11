# Chapter 2

1.
	> If a wavetable with 1000 samples is played back at unit transposition, at a sample rate of 44100 Hertz, how long does the resulting sound last?
	- 1000/44100 = 0.022675737

2.
	> A one-second wavetable is played back in 0.5 seconds. By what interval is the sound transposed?
	- An octave.

3.
	> Still assuming a one-second wavetable, if we play it back periodically (in a loop), at how many Hertz should we loop the wavetable to transpose the original sound upward one half-step?
	- 2^(1/12) * 44100 + 44100 = 90822.322461245

4.
	> We wish to play a wavetable, looping ten times per second, so that the original sound stored in the wavetable is transposed up a perfect fifth. How large a segment of the wavetable, in samples, should be played back?
	- A pitch a fifth up has a 3:2 frequency relationship to its base pitch. So, we should play 150% of the wavetable.
5.
	> Suppose you wish to use waveform stretching on a wavetable that holds a periodic waveform of period 100. You wish to hear the untransposed spectrum at a period of 200 samples. By what duty factor should you squeeze the waveform?
	- At a period of 200 samples, you want to stretch the waveform by 2.
6.
	> The first half of a wavetable contains a cycle of a sinusoid of peak amplitude one. The second half contains zeros. What is the strength of the second partial of the wavetable?
	- The second partial is?
7.
	> A sinusoid is stored in a wavetable with period 4 so that the first four elements are 0, 1, 0, and -1, corresponding to indices 0, 1, 2, and 3. What value do we get for an input of 1.5: (a) using 2-point interpolation? (b) using 4-point interpolation? (c) What's the value of the original sinusoid there?
	a. 1.5
	b. 1.5
	c. 
8.
	> If a wavetable's contents all fall between -1 and 1 in value, what is the range of possible outputs of wavetable lookup using 4-point interpolation?
	- -1 to 1.
