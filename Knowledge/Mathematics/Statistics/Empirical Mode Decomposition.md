Date: 04-03-2025
Tags: #Statistics #MachineLearning #Numerics 

## Motivation
With PCA and ICA, we so far considered data decomposition methods that are based on the statistical properties of the signals. The order in which our data was obtained did not play a role. Now we focus on methods for situations where the temporal structure of the data is important.
The Fourier transform decomposes signals into sinusoidal oscillations. This makes sense when analyzing linear time invariant systems because then oscillations are eigenfunctions. For nonlinear systems, eigenfunctions typically look different.
One approach to dealing with nonlinearity and non-stationarity is to decompose the signal into non-sinusoidal adaptively chosen oscillations. This is what empirical mode decomposition does.
## Method

Cubic spline interpolation is required to determine the EMD.

## Intrinsic Mode Function 
An intrinsic mode function (IMF) is a function $x: [t_0, t_1] \to \mathbb{R}$ such that
- The number of extrema and zero-crossings differs by at most one,
- and at any point, the mean of the envelopes defined by cubic spline interpolation of the local maxima and the local minima respectively is zero
## Sifting Process

The sifting process extracts a single IMF from a signal $x(t)$:
1. Find the minima and maxima of $x(t)$
2. Interpolate them with cubic splines to obtain the upper and lower envelopes
3. Compute the mean of the envelopes $m(t) = \frac{1}{2} [\theta_\min (t) + \theta_\max (t)]$
4. The difference between the data and the mean gives:
		$h(t) = x(t) - m(t)$
5. Return $h(t)$ if it is an IMF, or continue with $x(t) = h(t)$ as new data

### Shortcomings of Sifting Process
- Spline fitting can be problematic near the ends
- Over- and undershoots may generate new extrema
- The envelope mean may differ from the "True local mean"
- Too much sifting can also result in nonphysical IMFs

## Algorithm
1. Compute an IMF from the signal $x(t)$
2. Remove it from the signal
3. stop if the residue is small enough or repeat
The result is the decomposition: 
	$x(t) ) \sum_{k=1}^K c_k(t) + r_k(t)$, $c_k(t)=$ IMFs, $r_k(t)=$ residue.

The IMFs have decreasing average frequency. The last component can be the trend or a constant
Assumptions made for EMD:
- The signal has at least one maximum and one minimmum
- The characteristic time scale is defined by the time lapse between extrema

---
## References
[[Principal Component Analysis (PCA)]]
[[Independent Component Analysis (ICA)]]
[[Fourier Transform]]
[[Interpolation]]