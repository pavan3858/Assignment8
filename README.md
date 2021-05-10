# Assignment8
## Introduction
In this assignment, we want to explore how to obtain the DFT, and how to recover the analog Fourier Tranform for some known functions by the proper sampling of the function
### Assignment tasks
2.1 Review of Assignment Examples


2.1.1 Error on Reconstruction \
We find the Fourier transform and invert it back to the time domain for a random signal, find maximum error to test the reconstruction.\
from pylab import*\
x=rand(100)\
X=fft(x)\
y=ift(X)\
c[x,y]\
print(abs(x-y) .max ( ) )\
The maximum error obtained from the below code = 3.3941334505218686e-16

2.1.2 Spectrum of Pure Sinusoidal and Amplitude Modulated Signal

We use fft() and fftshift() commands available in Python to obtain the Spectrum of the signals sin(5t) and (1 + 0:1*cos(t))(cos(10t)).We choose appropriate sampling frequency and normalisation to obtain the required Spectrum .

x=linspace(0 ,2*pi , 129 ) ; x=x [ : -1 ] \
y=sin(5*x)\
Y=fftshift(fft(y))/128.0\
w=linspace(-64,63,128)

![Figure_8 1](https://user-images.githubusercontent.com/81006760/117629499-da904c80-b197-11eb-89d8-a04d32b01476.png)
Figure1-Fourier spectrum plot of sin(5t)

t=linespace(-4*pi,513);t=t[:-1]\
y=(1+0.1*cos(t))*cos(10*t)\
Y=fftshift(fft(y))/512.0\
w=linespace(-64,64,513);w=w[:-1]

![Figure_8 2](https://user-images.githubusercontent.com/81006760/117629764-1f1be800-b198-11eb-8dd0-952828809e2e.png)
Figure-2

Inorder to allow space for more frequencies it is essential to increase the number of samples taken, also only the phase at spikes are important for us.Hence, while plotting the angle,it is good to consider the magnitude as well

2.2 Spectrum of sin^3(t)andcos^3(t)
![Figure_8 3](https://user-images.githubusercontent.com/81006760/117629938-4a9ed280-b198-11eb-9684-8d706acf35ce.png)
Figure 3: Spectrum of sin^3(t)

![Figure_8 4](https://user-images.githubusercontent.com/81006760/117630140-846fd900-b198-11eb-8b06-fb3e565885ce.png)
Figure 4: Spectrum of cos^3(t)

2.3 Spectrum of Phase Modulated Wave
Consider the signal cos(20t +5cos(t)).Using the same helper function as before, we get the following output:

![Figure_8 5](https://user-images.githubusercontent.com/81006760/117630341-baad5880-b198-11eb-85c2-e0e7f35905bb.png)
Figure 5: Spectrum of cos(20t+5cos(t))

We observe the plot that its a Phase modulation since phase of the signal is varying proportional to amplitude of the message signal being ! = 20 and infinite side band frequencies which are produced by 5cost.Phase spectra is a mix of different phases from [-pi;pi] because of phase modulation, i.e since the phase is changed continuously with respect to time.



2.4 Continuous time Fourier Transform of a Gaussian

We observe the magnitude spectrum of e^-t2=2 and that it almost coincides with exact Fourier Transform plotted with accuracy of 1 : 32645e^-17in 3 iterations at the sampling rate of 512.

![Figure_8 6](https://user-images.githubusercontent.com/81006760/117630534-ed575100-b198-11eb-9ddd-8edd91104349.png)


The iteration used minimizes the error by increasing the window size and sampling rate. The optimal window size turns out to be 25.1327 s.
#### Conclusion
Hence we analysed the how to find DFT for various types of signals and how to estimate normalising factors for Gaussian functions and hence recover the analog Fourier transform using DFT ,also to find parameters like window size and sampling rate by minimizing the error.Also, FFT works well for signals with samples in 2^k, as it dividesthe samples into even and odd and goes dividing further to compute the DFT.



