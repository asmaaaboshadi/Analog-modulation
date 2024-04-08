# Analog-modulation
you can find a MATLAB assignment about analog modulation 
1) double sided band

1.1 INTRODUCTION
Double Sideband modulation is the easiest and most direct type of analog modulation. In this scheme, the
modulated signal is obtained using a directmultiplication ofthemodulating signal (i.e. themessage) by a cosine
carrier. This multiplication results in shifting the entire spectrum of the message to a center frequency defined
by the carrier frequency. The modulation is said to be double sideband transmitted carrier (DSB-TC) when the
carrier is transmitted along the modulation term. If the carrier term is omitted, the modulation is termed
double sideband suppressed carrier (DSB-SC). DSB-TC has a significant advantage in the receiver design (i.e.
the envelop detector). Also transmitting the carrier independently enables us to extract useful information
such as the carrier frequency which can be helpful for carrier synchronization. However, the DSB-TC loses to
the other variant (i.e. the SC) in terms of power efficiency.

1.2 AIM
In this experiment, you’re required to achieve the following:
1. Get familiar with the concept of DSB modulation, and itsparameters.
2. Study the performance of the DSBmodulation.
3. Examine different detectors (coherent detector, envelopedetector).
4. Study the performance of coherent detection in the presence of frequency or phase mismatch.
   
1.3 PROCEDURE
1. Use Matlab to read the attached audio file, which has a sampling frequency Fs= 48 KHz. Find the
spectrum of this signal (the signal in frequency domain). [audioread, fft , fftshift , plot]
2. Using an ideal Filter, remove all frequencies greater than 4 KHz.
3. Obtain the filtered signal in time domain and frequency domain, this is a band limited signal of BW=4
KHz. [ifftshift ,ifft]
4. sound the filtered audio signal (make sure that there is only a small error in the filtered signal)
[sound]
5. Modulate the carrier with the filtered signal you obtained, you are required to generate both types
of modulation (DSB-TC and DSB-SC). Choose a carrier frequency of 100 KHz. For the DSB-TC take the
DC bias added to message before modulation to be twice the maximum of the message (modulation
index =0.5 in this case).
Note: You will also need to increase the sampling frequency of the filtered audio signal, the
sampling frequency must be at least 2 times the carrier frequency, In this simulation use
Fs = 5 Fc . [resample]
You have to sketch the modulated signal of both DSB-TC & DSB-SC in frequency domain.

6. For both types of modulations (DSB-SC & DSB-TC), use envelop detector to receive the message
(assume no noise). Note: to obtain the envelope you can use the following matlabcommand.

envelope = abs(hilbert(modulated signal))

7. After the reception of both modulation types using envelope detector, sketch the received
signal in time domain, and Play the received signal back (Note: to sound signal after
demodulation process you have to decrease the sampling frequency again). What
observation can you make of this or which type of modulation the envelope detector can be
used with?

For DSB-SC, perform steps 9-10.

8. Use coherent detection to receive the modulated signal with SNR=0, 10, 30dB then sound the
received signals and plot them in both time and frequency domain.

9. Repeat the coherent detection with frequency error, F=100.1 KHz instead of 100 KHz and Find
the error. Do you have a name for this phenomenon?

10. Repeat the coherent detection with phase error = 200.



1.4 USEFUL MATLAB FUNCTIONS
audioread,fft, fftshift, ifft, ifftshift , plot, awgn, resample, sound, hilbert, abs, max.


1.5 HINT
You are not allowed to use built in functions like ammod, amdemod


2) single sided band

   
2.1 INTRODUCTION

The bandwidth inefficiency stemming from the DSB transmission was the main reason why the
single sideband (SSB) was developed. In SSB modulation, the bandwidth required for band pass
transmission is equal to the bandwidth of that of the baseband. In other words, the band
requirement for SSB is halved with respect to that of DSB which requires twice the baseband
bandwidth. This reduction in transmission bandwidth is possible since the sideband are replicated
twice over the positive and negative frequencies. However, the bandwidth reduction doesn’t come
entirely free. In fact, SSB suffers from several disadvantages that we hope to cover in the following
simulation.


2.2 AIM

In this experiment, you’re required to achieve the following:
1. Familiarize students with the SSB modulation scheme.
2. Study the performance of SSB with different detectors.
3. Investigate the disadvantages of the SSB
   
2.3 PROCEDURE

1. Use Matlab to read the attached audio file which has a sampling frequency Fs= 48 KHz. Find
the spectrum of this signal. (same as previous experiment)
2. Using an ideal Filter, remove all frequencies greater than 4 KHz. (same as previous experiment)
3. Obtain the filtered signal in time domain, this is a band limited signal of BW=4KHz. You could
play the sound back, to make sure only small distortion was introduced. (same as previous
experiment
4. Generate a DSB-SC modulated signal and plot its spectrum. Choose the carrier frequency
to be 100kHz. Remember to set the sampling frequency to Five times the carrier
frequency Fs = 5Fc. (same as previous experiment)
5. Obtain the SSB by filtering out the USB (we need to get LSB only) of the DSB-SC modulated
signal using an ideal filter then Plot the spectrum again.
6. Use coherent detection with no noise interference to get the received signal (to demodulate the
SSB-SC) and play the file back also sketch the received waveform and spectrum.
7. Repeat steps 5 and 6, only this time. Use a practical 4th order Butterworth filter. [butter, filter]
8. For the ideal filter case, get the received signal again but when noise is added to SSB-SC with
SNR = 0, 10, and 30 also play the received sound and sketch the received waveform/spectrum in
each case. [awgn]
9. For the ideal filter case, generate a SSB-TC. As with experiment one, set the DC bias to twice
the maximum of the message. Use envelope detector to demodulate the message (without noise)
. Play back the received message and sketch its waveform.

2.4 USEFUL MATLAB FUNCTIONS

audioread ,fft, fftshift, ifft, ifftshift , plot, awgn, resample, sound. , hilbert, abs, max, butter,filter.



3) frequency modulation

   
3.1 INTRODUCTION

Frequency modulation (FM) is a modulation type in which the instantaneous frequency of the carrier is
changed according to the message amplitude. The motive behind the frequency modulation was to
develop a scheme with inherent ability to combat noise. The noise, being usually modeled as additive, has
a negative effect on the amplitude by introducing unavoidable random variations which are superimposed
on the desired signal. Unlike the amplitude, frequency has a latent immunity against noise. Since it resides
“away” from the amplitude, any changes in the amplitude would be completely irrelevant to the
frequency. In other words, there is no direct correlation between the variation in amplitude and
frequency, thus making FM a better candidate over AM with respect to noise immunity. However, what
FM gains in noise immunity lacks in bandwidth efficiency. Since FM usually occupies larger bandwidth, AM
is considered more bandwidth wise.

3.2 AIM

In this experiment, we investigate the narrowband frequency modulation when the SNR is varied.
Students are expected to:
1. Develop an appreciation of FM ability to counteract noise.
2. Be able to simulate the generation and the demodulation of NBFM using matlab.
3. To be able to tell the similarities and differences between AM and NBFM.
   
3.3 PROCEDURE

1. Repeat steps 1 through four in experiment 1,2.
2. Generate the NBFM signal. Use a carrier frequency of 100kHz and a sampling frequency of Fs =
5Fc . Plot the resulting spectrum. What can you make out of the resulting plot?
3.what is the condition we needed to achieve NBFM.
4. Demodulate the NBFM signal using a differentiator and an ED. For the differentiator, you can
use the following command: diff. Assume no noise is introduced.

3.4 USEFUL COMMANDS
audioread, fft, fftshift, ifft,ifftshift, awgn, upsample,resample, sound,hilbert, abs,mean,cumsum,diff.
