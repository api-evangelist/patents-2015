---

title: Circuit and method for clock recovery of quadrature amplitude modulated waveforms
abstract: Apparatus and method for performing low cost analog clock recovery within a high bandwidth radio frequency communications system. An analog data source is passed through a squaring loop typically utilized for carrier recovery. A squaring loop consists of an analog mixer to multiply one component of the complex signal with itself, a bandpass filter and phase lock loop. The addition of nonlinear gain compression enables clock recovery for higher order modulation schemes to exploit the fundamental phase differences of the individual components that construct the received signal. The output of the phase lock loop drives the Analog-to-Digital converter. It is desired that this signal converges to the symbol clock's frequency and phase of the transmitter, thereby sampling the received baseband signal at the desired symbol levels.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09313018&OS=09313018&RS=09313018
owner: The United States of America as represented by the Secretary of the Air Force
number: 09313018
owner_city: Washington
owner_country: US
publication_date: 20150512
---
The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

This invention relates generally to high bandwidth radio frequency receivers and more specifically to radio frequency receivers wherein blind recovery of a transmitter symbol clock is necessary for reconstruction of data at that receiver.

Clock recovery of a transmitted radio frequency waveform is necessary when digitally sampling the analog waveform at a receiver. The recovered clock must be phase and frequency locked to the transmitted symbol clock and with sufficiently low noise to reduce the likelihood of sampling the analog data at a non ideal point in time. Clock recovery is necessary for many wireless communication systems. However some scenarios exist which provide a challenge to adequate recovery.

When a phase locked reference signal is transmitted alongside its digital to analog converted DAC waveform a receiver can use the reference signal to sample the received data at the analog to digital converter ADC . Often however a reference signal is not sent with a waveform and thus must be derived from the data itself. This type of blind recovery of a transmitted symbol clock can be challenging for simple modulation schemes such as Binary Phase Shift Keying BPSK and Quadrature Phase Shift Keying QPSK and becomes a more significant challenge for high order Quadrature Amplitude Modulation QAM schemes such as 16 QAM. This is because most blind recovery schemes rely on regular zero crossings in the data to derive the reference frequency. With high order modulation data the number of zero crossings is potentially reduced and the recovery technique may have trouble making a decision on the clock frequency.

In addition to this challenge many recovery schemes are designed to recover the clock of a single modulation scheme. Dynamic modulation techniques such as those with the ability to adjust to changing atmospheric or topological conditions means a recovery technique must be powerful enough to support these changes while maintaining relatively low cost and complexity.

Finally a number of clock recovery solutions exist which rely on the ability to oversample received data and thereby reconstruct a reference clock in the digital domain. However as signal bandwidths continue to increase the reliance on high speed ADCs to sufficiently oversample that signal is also increasing along with cost and complexity of the intended receiver.

An optimal solution to the blind recovery of a high order modulation symbol clock should be one that is relatively simple low cost and does not require oversampling of a received waveform at the ADC. The prior art has been able to isolate some of these parameters independently but has failed to optimize for all parameters at once.

In U.S. Pat. No. 5 982 200 a Costas loop is identified to perform carrier recovery of a waveform. This provides the ability to recover a signal s center operating frequency and downconvert to a lower frequency or baseband. This Costas loop utilizes two square law circuits to perform recovery of the carrier sinusoid. However this operation targets carrier recovery as opposed to clock recovery and targets QPSK as opposed to high order modulation schemes.

In U.S. Pat. No. 5 519 733 carrier recovery of high order modulation is performed using a phase detection system with a phase lock loop. While providing detection of high order QAM the patent uses a more complex detection system than the squaring law and recovers the carrier of a waveform as opposed to the sinusoidal clock signal.

In U.S. Pat. No. 6 278 741 a software based timing recovery technique is presented. While this technique is potentially powerful for low bandwidth applications where a receiver ADC can oversample a waveform to achieve more flexibility of design in the software domain such a method is impractical for high bandwidth signals due to limitations of ADC sample rates.

In U.S. Pat. No. 5 825 825 an analog clock recovery technique is shown for recovery of the fundamental sinusoid from a baseband waveform. This process has the potential to recover a clock from a high order QAM waveform. However the design is complex requiring multiple digital to analog and analog to digital waveform conversions and components. Additionally the technique requires high speed digital components which may not support high frequency clock recovery.

In U.S. Pat. No. 7 933 362 a detection technique is presented which utilizes pilot signals and unique word synchronization for recovery. Such a method can be used efficiently without the need for a squaring loop implementation. However since this technique requires pilot tones it fundamentally requires a synchronization sinusoid to be sent along with the target data. This minimizes the bandwidth dedicated to data transmission and is no longer considered a blind clock recovery detection technique. Depending on the implementation an oversampling ADC may also be required.

It is therefore an object of the present invention to provide an apparatus that overcomes the prior art s dependency on costly oversampling receiver ADCs to perform symbol clock recovery of high order QAM in the analog domain.

It is a further object of the present invention to provide a reduction in analog radio frequency components in the clock recovery design such that a symbol clock may be recovered from any QAM waveform without additional circuitry or complex analog switching circuitry.

It is still a further object of the present invention to provide an apparatus wherein a symbol clock can be derived from a QAM waveform blindly without transmitting a phase locked version of the DAC clock or other a priori knowledge thereby only relying on the downconverted waveform itself.

It is yet still a further object of the present invention to provide an apparatus that is capable of recovering a symbol clock from both narrow band and wide band signals where as the blind recovery process occurs regardless of data rate or occupied spectral bandwidth and relies only on the frequency of the original symbol clock.

Briefly stated the present invention achieves these and other objects through the use of the square law timing recovery SLTR method more generally used for low order carrier recovery.

SLTR is a simple and widely used recovery method for recovering sinusoidal synchronization signals in cases where a synchronization signal is not provided from a communications transmitter to a receiver. Recovery of such a sinusoid is generally one which is phase locked as well as a frequency multiple of the carrier clock. Thus SLTR is generally used for downconverting a radio frequency RF or intermediate frequency IF waveform to its baseband equivalent.

In the case of carrier recovery of amplitude modulated waveforms the order N of the squaring block is generally chosen such that it is equivalent to the order of the received waveform y t . For example a 2 QAM waveform BPSK would require a squaring block of order N 2 while a 4 QAM QPSK waveform would require an order of N 4. The reason for this is shown in Equations 1 2 for a BPSK waveform. cos 0 180 degrees 1 2 1 cos 2 2 2 0 360 degrees 2 2 cos 2 2 

The BPSK waveform y t is shown in Equation 1 where A is some amplitude is the fundamental frequency and is the phase. Squaring the BPSK waveform gives rise to a DC term as well as a sinusoid at twice the fundamental frequency as shown in Equation 2 . While the original BPSK waveform exhibited a phase component dependent on the value of the transmitted data the phase information in Equation 2 has been canceled out. A bandpass filter is then applied to the signal to remove the unwanted DC component and isolate the desired reference frequency. A similar process can be shown using QPSK with the squaring order N 4.

However this process breaks down when attempting to apply it to higher order modulation schemes such as 16 QAM. In this case all transmitted symbols are not even phase multiples of 360 degrees and thus repeated squaring processes will not eliminate all phase components. Because of this SLTR is generally not considered for signal orders higher than QPSK.

Even so the SLTR process can be applied to clock recovery of baseband 16 QAM and higher order QAM signals which is the basis of this invention. This is because once the QAM waveform has been downconverted to baseband it is separated into its original in phase and quadrature phase components. Each of these components are fundamentally an amplitude modulated BPSK waveform. By passing the downconverted in phase or quadrature phase signal shown in Equation 3 through a second order squaring block as identified in Equation 4 the following process occurs. cos 0 180 degrees 3 2 1 cos 2 2 2 0 360 degrees 2 2 cos 2 4 

As in the BPSK carrier recovery example the squared signal in Equation 4 is filtered to remove the DC component and leave a sinusoid at twice the original fundamental frequency. Because each downconverted QAM channel consists of only two phase components separated by 180 degrees the order of the squaring block will never need to be higher than N 2 for any order QAM signal. Unlike the BPSK example an additional gain term x exists which results in an additional amplitude modulation. This term can be removed with an amplifier operating in compression or other non linear device. This process is not unique to 16 QAM but can be applied to any order square QAM scheme using an N 2 square law.

Therefore it is accurate to say that while the present invention 1. utilizes square law timing recovery as the prior art requires to achieve the same 2. and while the present invention can blindly recover a waveform s symbol clock as prior art requires to achieve the same the present invention provides a solution lacking in the prior art because it 3. can blindly recover the symbol clock for high order QAM without the need for oversampling of the waveform at the receiver ADC or complex switching of analog hardware as the QAM waveform s order changes. As such the present invention represents a significant departure from prior art methods.

According to an embodiment of the invention apparatus for performing blind clock recovery of high order QAM comprises a squaring block to square the incoming QAM waveform a bandpass filter with a frequency bandwidth sufficiently small to provide adequate recovery signal to noise ratio a non linear device such as a comparator or amplifier operating in compression to remove amplitude modulation and a phase lock loop to reduce phase noise and derive the resultant sinusoid.

The above and other objects features and advantages of the present invention will become apparent from the following description read in conjunction with the accompanying drawings in which like reference numerals designate the same elements.

Referring to the key components of the blind clock recovery scheme are the analog baseband data source the analog clock recovery circuit and ADC . The baseband data source consists of in phase and quadrature phase components. The present invention is able to operate on either the in phase signal at or the quadrature phase signal at however it is shown in that the in phase component at is used. This signal is coupled by allowing the signal to be used for clock recovery and data sampling .

Still referring to the signal at enters the analog clock recovery circuit and is split once more by creating two identical signals at and at in terms of content and power level. The squaring of the signals at and at is performed by mixer resulting in the signal at . The tone located around 1.4 GHz in is the symbol clock and signal of which to recover. Referring back to the output signal at is bandpass filtered by to isolate the symbol clock tone resulting in the signal at . This signal has extensive amplitude modulation due to the multiple signal levels conveying information by the higher order modulation. A nonlinear gain compression device is used to remove the variation of signal envelope creating the signal at . This signal is the input to a standard phase lock loop PLL which converges to the desired symbol clock. The output signal at drives the frequency and phase of the ADC sampling . The ADC clock is continually refined with incoming data to counteract any channel impairments or platform mobility causing drift on the symbol clock.

Referring to the analog baseband signal in phase component s spectrum is shown. This is frequency domain representation of the signal at .

Referring to the analog spectrum of the signal at is shown. This is frequency domain representation of the signal after squaring the in phase component of the received signal.

Referring to the analog spectrum of the signal at is shown. This is frequency domain representation of the signal after bandpass filtering the square of the in phase component of the received signal.

Referring to the analog signal at is shown. This is the time domain representation of the signal after bandpass filtering the square of the in phase component of the received signal.

Referring to the analog signal at is shown. This is time domain representation of the signal after passing the bandpass filtered signal at through nonlinear gain compression .

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to those precise embodiments and that various changes and modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

