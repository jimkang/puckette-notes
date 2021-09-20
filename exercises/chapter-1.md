# Chapter 1

1. 
	> A sinusoid has initial phase phi = 0 and angular frequency omega = pi/10. What is its period in samples? What is the phase at sample number n=10?
	- The period is 2 * pi/omega. 2pi is a full rotation, and omega, the angular frequency, is how often that rotation happens. So: 2pi/(pi/10) = 20 samples.
	
		<iframe src="https://www.desmos.com/calculator/vtbz60ipo7?embed" width="500" height="500" style="border: 1px solid #ccc" frameborder=0></iframe>
	
	- The phase at n = 10 is pi/10 * 10 = pi.


2.
	> Two sinusoids have periods of 20 and 30 samples, respectively. What is the period of the sum of the two?
	- It's the least common multiple: 60.
	<iframe src="https://www.desmos.com/calculator/biyhdr8qp9?embed" width="500" height="500" style="border: 1px solid #ccc" frameborder=0></iframe>

3.
	> If 0 dB corresponds to an amplitude of 1, how many dB corresponds to amplitudes of 1.5, 2, 3, and 5?
	- `d = 20 * log10(a/a0)`
	|a|formula|dB|
	|--|--|--|
	|1.5|20 * log10(1.5/1)|3.4|
	|2|20 * log10(2/1)|6|
	|3|20 * log10(3/1)|9.4|
	|5|20 * log10(5/1)|14|


4.
	> Two uncorrelated signals of RMS amplitude 3 and 4 are added; what's the RMS amplitude of the sum?
	- RMS is `sqrt(meanPower(signal))`. meanPower is  `x.reduce((sum, sample) => abs(sample)^^2 + sum))/x.length`. 
	- The mean power of a signal with a=3 is 9. The mean power of a signal with a=4 is 16.
	- The mean power of those two signals combined will be 25, so the RMS will be 5.


5.
	> How many uncorrelated signals, all of equal amplitude, would you have to add to get a signal that is 9 dB greater in amplitude?
	- Decibel formula: `d = 20 * log10(a/a0)`
	- When a = a0, you get 0 db.
	- The amplitude of a0 + a0 is 2a0, etc.
	- `9 = 20 * log10(x * a0)`
	- `9/20 = log10(x * a0)`
	- `10^(9/20) = x * a0`
	- x = 2.818/a0 ?


6.
	> What is the angular frequency of middle C at 44100 samples per second?
	- Middle C's frequency is 261.63 Hz.
	- At R = 44100, each cycle/period is 44100/261.63 = 168.5 samples.
	- The period is 2 * pi/omega. 2pi is a full rotation, and omega, the angular frequency, is how often that rotation happens.
	- omega = 0.037 ?


7.
	> Two sinusoids play at middle C (MIDI 60) and the neighboring C sharp (MIDI 61). What is the difference, in Hertz, between their frequencies?
	- Middle C's frequency is 261.63 Hz.
	- In equal temperament, C# is going to be 1/12 of the way between C and C an octave up (523.26).
	- (523.26-261.63)/12 = 21.8025 Hz


8.
	> How many cents is the interval between the seventh and the eighth harmonic of a periodic signal?
	- The 7th and 8th harmonics have angular frequencies of 7w and 8w (or is it 8w and 9w?).
	- Hz = cycle/s
	- w = radians/s
	- radians to cycles: Cycle is a period
	- Period: 2pi/w
	- Hz = (2pi/w)/s
	- 2pi/8w - 2pi/7w Hz => How many cents is this? Depends on w, I thought.


9.
	> If an audio signal has peak amplitude 1, what is the minimum possible RMS amplitude? What is the maximum possible?
	- Mininmum: Something close to 0 but not 0, depending on N.
	- Maximum: 1
