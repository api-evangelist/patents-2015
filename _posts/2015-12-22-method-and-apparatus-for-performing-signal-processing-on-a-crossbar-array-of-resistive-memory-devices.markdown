---

title: Method and apparatus for performing signal processing on a crossbar array of resistive memory devices
abstract: Invention provides an apparatus and method for performing signal processing on a crossbar array of resistive memory devices. The invention is implemented using one or multiple crossbar arrays of resistive memory devices in conjunction with devices for converting input real number representations to voltage waveforms, devices for converting current waveforms into voltage waveforms, and devices for converting voltage waveforms to real numbers outputs.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09455030&OS=09455030&RS=09455030
owner: The United States of America as represented by the Secretary of the Air Force
number: 09455030
owner_city: Washington
owner_country: US
publication_date: 20151222
---
The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

As demand on high performance computation continuously increases the traditional Von Neumann computer architecture becomes less efficient. In recent years neuromorphic hardware systems have gained great attentions. Such systems can potentially provide the capabilities of biological perception and information processing within a compact and energy efficient platform. Systems such as these can be used in different computing platforms for high performance computing under size weight and power SWaP constraints. Potential Air Force applications for example include autonomy and autonomous systems communication and networking intelligence data analytics and cyber situational awareness.

To this end a resistive crossbar array based computing system has the potential to enable high efficient large scale signal processing. Such systems for example can dramatically improve the capabilities in pattern recognition used in modern artificial intelligence systems. In such systems a crossbar array of resistive memory devices is used to carry out signal processing computations.

The present invention relates generally to methods and apparatuses for sensing the current that represents the computation results from a resistive memory device i.e. memristor crossbar array and converting it to a digital word using low power circuit with small form factor.

It is an object of the present invention to design an apparatus and method that transforms an input digital word into a distinct output digital word as a function of the current and voltage the input digital word generates across an array of resistive memory devices.

In an embodiment of the present invention an apparatus for a resistive memory array signal processor comprises a first converter for converting a real number vector input into a temporal sequence of voltage waveform outputs at least one resistive memory array having the sequence of voltage waveforms as inputs for converting the sequence of voltage waveforms into current waveform outputs an integrator for accumulating the current waveform outputs a second converter having the accumulated current waveforms as inputs for converting the accumulated current waveforms into voltage waveform outputs and a third converter having the voltage waveforms as inputs for converting the voltage waveforms into a real number output.

In another embodiment of the present invention a method for performing signal processing using a crossbar array of resistive memory devices comprises the steps of a first mapping of a real number input to a voltage waveform applying the voltage waveform to a plurality of wordline inputs of the crossbar array of resistive memory devices accumulating current waveforms through each of a plurality of bitline outputs of the crossbar array of resistive memory devices integrating the accumulated current waveforms converting the integrated current waveforms to voltage waveforms and a second mapping of the voltage waveforms to a real number output.

Briefly stated the present invention provides an apparatus and method for performing signal processing on a crossbar array of resistive memory devices. The invention is implemented using one or multiple crossbar arrays of resistive memory devices in conjunction with devices for converting input real number representations to voltage waveforms devices for converting current waveforms into voltage waveforms and devices for converting voltage waveforms to real numbers outputs.

The above and other objects features and advantages of the present invention will become apparent from the following description read in conjunction with the accompanying drawings in which like reference numerals designate the same elements.

The present invention provides an apparatus and method for performing signal processing on a crossbar array of resistive memory devices using pulse based representations of input and output values. The invention is implemented using one or multiple crossbar arrays of resistive memory devices in conjunction with devices for converting real number representations to voltage waveforms devices for converting current waveforms into voltage waveforms and devices for converting voltage waveforms to real numbers all of which may be implemented in electronic hardware or electronic hardware augmented by firmware or computer software.

Relying on a one to one mapping between a mathematical value and a pulse based voltage waveform each individual input value can be represented by a temporal sequence of voltage pulses applied to a wordline row of the crossbar array. The resistive crossbar design converts the input voltage pulse waveforms into output current waveforms at the bitlines column of the crossbar array. An integrator block is used to convert the output current waveform to a total accumulated current value. The accumulated current of each output of the crossbar is then converted back into pulse based voltage waveform using the reverse of the same with a different scale factor one to one mapping function for the input conversion.

This describes the apparatus and method for performing signal processing using pulse based representations of the inputs and outputs through a crossbar array of resistive memory devices.

The basic circuit of the invention s crossbar array with N rows and M columns of resistive memory devices is shown in the . For each pair of wordline WL and bitline BL there is one resistive memory device memristor connecting them. This embodiment of the present invention assumes that the conductance of the resistive memory device connecting WLand BLis set at g.

When voltage waveforms vi t j 1 2 . . . N are applied to the wordlines inputs also assuming that the bitlines are all held at 0 Volt the current waveforms io t at the end bottom of each of the bitlines can be calculated by 1 2 . . . 1 The integration of the current waveforms and the output current waveforms over a period of time T resulting from all the bitlines is represented by 1 2 . . . 2 

Referring to depicts alternative implementations of the crossbar array shown in . Within the scope of the present invention the resistive memory device 1R structure shown in can be replaced with either the 1S1R structure of serially connected one resistive memory 1R device and one 1S device shown in or the 1T1R structure connected one resistive memory 1R device and one transistor 1T device shown in .

Referring to the present invention based on the design of the crossbar array of resistive memory devices is now functionally depicted. The input to the system is a vector a a a where a j 1 2 . . . N is a real number. A one to one conversion mapping function converts the input real numbers into pulse base voltage waveforms in the time period of 0 T . The conversion mapping process can be written as 0 1 2 . . . 3 

Where vi t is a pulse based voltage waveform which means that vi t can only be one of the two predefined voltage levels Vand V. An example of the pulse based voltage waveform in time period 0 T is shown in . When these voltage waveforms are applied to the wordlines of the crossbar array see current waveforms are generated at the end of the bitlines see according to Equation 1 . A conversion module function CF is then used to convert each current waveform into pulse based voltage waveform CF 0 1 2 . . . 4 Note that with more than one input voltage waveforms applied the output current may not follow a pulse based waveform. Finally the invention applies another one to one conversion mapping function that converts output pulse base voltage waveforms in the time period of 0 T into real numbers. The conversion mapping process can be written as 0 1 2 . . . 5 

Please also note that the first and last conversion mapping steps can be omitted if the system is already using pulse based representations.

For the embodiment of the present invention described in the previous section there can be many choices of the conversion mapping functions M Mand CF. Specific implementations of the conversion mapping functions are possible.

If the input voltage waveforms of t are restricted to periodical pulse functions with fixed pulse width of T function Mcan be implemented by mapping the real number ato a unique frequency value of the pulse waveform such that 1 2 . . . 6 

For converting function CF from io t to vo t the accumulated total current by integrating io t over time period 0 T can be first calculated according to 1 2 . . . 7 

Again restricting the waveforms of t to periodical pulse functions with fixed pulse width of T the invention maps the accumulated total current to a unique frequency value of the vo t pulse waveform such that 1 2 . . . 8 

After obtaining the vo t waveforms the mapping function Mis implemented by mapping the frequency value of vo t to the real number bi such that 1 2 . . . 9 

If Equations 2 6 7 8 and 9 are combined the complete process performed by the present invention from inputs a 1 1 2 . . . N to outputs b i 1 2 . . . M can be captured as 

