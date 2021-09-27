# Chapter 1

- Note: Helpful to remember that everything is between -1.0 and 1.0 in these equations.

### Amplitude

- The *window* of samples that an amplitude applies to must be specified in order for that amplitude to be meaningful.
- Peak amplitude is the greatest sample in abs. value in the window.
- RMS (root mean square) amplitude:
	- `sqrt(meanPower(signal))`
	- Mean power:
		- `x.reduce((sum, sample) => abs(sample)^^2 + sum))/x.length`
			- Implicitly, "power" refers to the value of a squared sample.
		- Capital `P` usually means "mean power."
	- Always lower than peak amplitude.

### Superposing signals

AKA adding two signals together.

- The peak of the sum of two signals will never be greater than the sum of the peaks of each of the component signals.
- Same with the RMS.
	- RMS: I've seen this everywhere without knowing what it was.
- The mean power of the sum is the sum of the mean power of each signal *plus* 2 times the **covariance** of the two signals.
	- Covariance is `pairArrays(x, y).sum((total, samplePair) => sum + samplePair[0] * samplePair[1])/x.length` where x and y are assumed to have equal lengths.
		- If you multiply 0.5 by 0.5, you get 0.25. If you multiply 0.5 by -0.5, you get -0.25. So, the higher the covariance, the more the signals correlate. Weirdly, `[0.1, 0.1]` and `[0.1, 0.1]`  have a covariance of 0.01, but `[1, 1]` and `[1, 1]`  have a covariance of 1. So does that mean the second set is ten times as correlated?
			- Ah, [apparently not](https://en.wikipedia.org/wiki/Covariance):
				> The magnitude of the covariance is not easy to interpret because it is not normalized and hence depends on the magnitudes of the variables. The [normalized version of the covariance](https://en.wikipedia.org/wiki/Covariance_and_correlation "Covariance and correlation"), the [correlation coefficient](https://en.wikipedia.org/wiki/Pearson_product-moment_correlation_coefficient "Pearson product-moment correlation coefficient"), however, shows by its magnitude the strength of the linear relation.
