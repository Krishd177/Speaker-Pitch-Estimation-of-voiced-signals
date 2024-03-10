# Speaker-Pitch-Estimation-of-voiced-signals

Speech can be seen as the output of a linear time-varying system slowly varying its properties with time. Small segments of speech can be interpreted as a time invariant system.
Pitch: - Pitch is the fundamental frequency of the signal. The fundamental frequency is defined as the lowest frequency of a Periodic signal. Every speech segment can be formed out of it.
For analysis of speech signals, we use Homomorphic filters. 
Before understanding concept and applications of Homomorphic filters we must define some new terminologies: -

●	Cepstrum: - 
Scientists Bogert, Healy, and Tukey observed that the logarithm of the power spectrum of a signal consists of the logarithm of the signal spectrum plus a periodic component due to the noise(echo). A periodic component can help us understand new parameters of a signal. Hence, cepstrum is introduced.
“The cepstrum of a signal is the inverse discrete time Fourier transform (IDTFT) of the logarithm of the magnitude of the DTFT of the signal.”

                                 
Where,                        
                                 

●	Homomorphic: - 
From correlation of the vector space theory and signal operations it was observed by Oppenheim that classes of nonlinear systems could be defined on the generalized principle of superposition and such systems were called homomorphic. The principle of superposition simply states that if an input signal is composed of a linear combination of elementary signals, then the output is a linear combination of corresponding outputs.




Problem Description

Why don’t we use simple IIR and FIR filters for pitch detection: -
❖	Simple filters are less sensitive towards additive noise which can contribute to pitch estimation and give errors in pitch estimation. Meanwhile homomorphic filters remove the undesired part, giving accurate pitch.
❖	Simple filters are designed for a particular range if the Pitch falls in the restricted region, it can cause loss in pitch. A speech signal always varies in pitch making it difficult to recognize the actual pitch.
❖	Pitch is harmonic of fundamental frequency. Sometimes simple filter cannot distinguish between pitch and frequency.

To tackle the above listed problems, we use a homomorphic filter for pitch detection. The problem of speech analysis is to estimate the parameters of the speech model and to measure their variations with time. Since the excitation and impulse response of a linear time-invariant system are combined in a convolutional manner, the problem of speech analysis can also be viewed as a problem in separating the components of a convolution. This problem is often called "deconvolution".

 To solve this problem homomorphic filters are used.

A homomorphic filter is a homomorphic system that lets the desired signal unaltered and undesired signal completely removed. Where the input signal is a convoluted signal and the output is also a convoluted signal. In our case it basically implies the above cepstrum function. Here the linear function is the logarithmic of the dft of the signal.

 
figure 1. basic structure of Homomorphic filter. (1)

where, D*   represents the convoluted signal
            L     represents the linear operation between two signals
            D-* represents the inverse of D*



This characteristic system is defined by the property that when x[n] = x1[n] ∗ x2[n], the corresponding output is 

 

That is, the characteristic system transforms a combination by convolution into a corresponding combination by addition. The middle system in Fig. 2 is the system denoted L{}, which is an ordinary linear system satisfying the principle of superposition with addition as both the input and output operation for signal combination. Finally, the inverse characteristic system must transform a sum into a convolution so that the overall system transformation satisfies

 

 
 figure 2. DTFT representation of the characteristic system for convolution (1).

The inverse of the characteristic system for convolution is depicted in Fig.3. It is obtained by simply using the complex exponential to invert the effect of the complex logarithm.

 
 figure 3. DTFT representation of the inverse characteristic system for convolution (1).



The output of the characteristic system for convolution is the complex cepstrum. This is not because the complex cepstrum is complex; indeed, if x[n] is real, then xˆ[n] will also be real. Rather, the modifier complex is used to imply that the complex logarithm is used in the computation of the complex cepstrum. The complex logarithm is defined as 

 

where if X(eiω) = X1(eiω) · X2(eiω), as for the convolution x[n] = x1[n] ∗ x2[n], then the following must hold: 

 

The relationship between the cepstrum and complex cepstrum can be obtained by noting that, if x[n] is real, then log |X(eiω) | is a real and even function of ω, while arg{X(eiω)}, the imaginary part of Xˆ(eiω), is a real and odd function of ω. 

This implies that
 

That is, as we have defined them, the cepstrum is the even part of the complex cepstrum.





