---

title: Speaker protection for surround sound systems
abstract: An audio/video receiver configured to limit the power delivered to its speakers based on real time calculations. First, power delivered to the speakers is limited to the power rating of the speakers during short durations. Second, a secondary longer time constant Root-Mean-Square (RMS) detector limits sustained power to the speakers for a predetermined fraction of the peak power rating.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09549256&OS=09549256&RS=09549256
owner: CRESTRON ELECTRONICS, INC.
number: 09549256
owner_city: Rockleigh
owner_country: US
publication_date: 20150205
---
This present invention provides a system and method for protecting audio speakers and more specifically one that prevents the speakers from getting damaged regardless of audio content and user settings.

The dynamic range of audio content intended to be used with a surround sound system can lead to damage to speakers when played at high volumes. In addition the typical surround sound system is constructed with an audio amplifier that provides the same available power to all speakers while most systems have a mixture of large and small speakers.

A common configuration for actual surround sound installation may involve for example a pair of large floor standing front speakers one located to the left and right of a display a smaller center channel speaker located above the display one located below or behind the display screen and a number of small satellite speakers for surround and back channels.

Typically the power handling capability of any large front speaker is usually significantly higher than the power handling capability of any center channel and surround channel. However it is typical for amplifiers used for this application provide identical power to all of these speakers. As a result this can lead to over driving the smaller speakers for example during playback intense audio action sequences. Moreover most speakers are rated for short term power usage and cannot sustain operation continuously at this power rating. Likewise if an end user operates a system at excessive volume settings speaker coils may become damaged for example through overheating.

A typical home theater uses an A V receiver is a device that provides an input selector switch a surround sound decoder a volume control function and a power amplifier to drive speakers. With the latest high definition audio formats provided by BlueRay players a powerful Digital Signal Processor DSP is necessary to decode and process surround sound content. Normally additional signal processing is required to perform post processing such as bass management dynamic range processing and equalization.

Typically dynamic range processing is usually limited to providing a midnight mode to reduce the dynamic range of the signals so that any on screen transients like gun shots and explosions don t wake up the neighbors. However this type of processing is not intended to protect the speakers and can even increase the likelihood of thermal damage. Since the peak power gets limited in midnight mode the end user does not hear the undesirable sounds like clipping and short term speaker overload that would normally trigger the user to turn the volume down. Instead the speaker continues to heat up until the point of failure.

There is a desire to prevent damage to audio speakers. Accordingly there is a need for an improved speaker protection for surround sound systems devices and methods.

It is to be understood that both the general and detailed descriptions that follow are exemplary and explanatory only and are not restrictive of the invention.

The instant invention provides a system and method of installing an audio system that prevents the speakers from getting damaged regardless of the audio content and user settings.

According to one aspect during the initial installation of a surround sound system the installer may program certain parameters related to the location of all audio speakers. These parameters may include among others the crossover frequency used for bass management the distance from the primary seating position and a volume trim that balances the Sound pressure level SPL level for each speaker at this seating position.

In other aspect the installer may enter two additional parameters related to the speakers used. Specifically the impedance of the speakers used and the power rating of the speakers used.

Audio speakers may be deployed in groups of similar types in addition to utilizing differently sized speakers e.g. front center surround and back. 

In an Audio Video Receiver AVR the gain of the built in amplifier is normally known therefore the power delivered to the speakers can be calculated using several parameters including the digital signal level input to the Digital to Analog Converter DAC converter the analog volume control gain which is in between the DAC and the power amplifier and the gain of the power amplifier. Accordingly a DSP can be configured to limit the power delivered to the speakers based on these calculations in real time.

The present invention seeks to overcome or at least ameliorate one or more of several problems including but not limited to mitigating audio speaker damage regardless of audio content and user settings. Additional aspects and advantages of the invention will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the invention.

The present invention advantageously utilizes a speaker protection module to protect one or more audio output devices.

The disclosed speaker protection module may be generally practiced with a diversity of Audio Video receivers and is particularly well suited in a hardware AVR having a surround sound DSP processor. However any reference to use of a specific type of AVR is provided by way of example and is not intended to limit the practice of the invention.

There are two mechanisms that tend to damage speakers. The first is mechanically induced damage caused by excessive excursion of the speaker. This type of failure is caused by over powering the speaker even for a short duration.

The second mechanism that damages speakers is thermal related. Excessive power for an extended period can cause various failure modes such as melting of the voice coil. The thermal failure mode can happen at power levels well below the speaker rating if applied over time.

In one embodiment a dual action protection system is deployed where the peak power delivered to the speaker is limited to the power rating of the speaker for short durations and then a secondary longer time constant Root Mean Square RMS detector limits the sustained power to the speaker is limited to a predetermined fraction of the peak power rating to prevent heat related failures.

Referring to shows an exemplary surround sound setup suitable for use with an embodiment of the present invention. An Audio Video Receiver AVR includes a speaker protection module implemented in a digital signal processor DSP for protecting one or more audio speakers . As would be understood by one skilled in the art the number location and configuration of speakers shown in are purely exemplary and may be varied.

Each speaker is connected to AVR through either a wired connection or a wireless connection. The wired connection may be analog or digital. The wired connection may utilize a standard protocol such as for example Universal Serial Bus USB Ethernet RS232 RS422 and can optionally also carry power using for example USB or Power Over Ethernet POE . The wireless connection may include but is not limited to ultrasound radio frequency RF ultra high frequency UHF and or infrared IR . Optionally the wireless connection may utilize a standard protocol such as for example Bluetooth WiFi Zigbee and or Digital Enhanced Cordless Telecommunications DECT .

Moreover some or all of the speaker protection module functionality described herein as being associated implemented in digital signal processor DSP could be implemented using another component or a combination of components in addition to or instead of DSP including but not limited to one or more personal computers PCs decoders and or sound processors.

In order to calibrate the speaker protection module for speakers a user typically an audio system installer designates values for the parameters used by the speaker protection module to calculate the speaker protection settings. Parameter values can be designated for example using any mobile computing device running graphically based commissioning software toolbox operative to communicate the aforementioned parameter values to AVR .

In the preferred embodiment the speaker protection module parameters include speaker impedance maximum speaker power amplifier gain and maximum DAC output voltage. Initially the speaker protection module of the AVR has to determine the threshold i.e. the maximum voltage level that the speakers can sustain.

The maximum voltage that the speaker can accept can be calculated using the rated speaker power and the speaker impedance the

The threshold is the fraction of full scale output that the speaker can sustain without failure. This number must be translated to a digital number for the DSP . The maximum level inside the DSP is called the full scale. This is represented in dB as dBFS and will map to the maximum output voltage at the output of the amp.

The value of threshold is programmed into the DSP . The DSP then limits the output voltage to this level thus protecting speaker . The speaker protection module prevents the amplifier from clipping and the speaker from overloading which results in better sound quality from the user s perspective. This advantageously prevents amplifiers from shutting down from faults caused by overheating and over current. Furthermore it does not rely on measuring the voltage and current going into the speaker therefore does not increase the cost of a AVR assuming there is enough spare DSP processing power in the unit. The operation of this speaker protector works regardless of the content played and user volume tone control and equalization settings. The end result is a system that is very difficult to damage.

The gain of the amplifier can be entered during the setup process for systems that have separate components implementing the surround processor and power amplifier. The gain information may be found for example in the amplifier s manual. Passive subwoofers can be protected using the same mechanisms since they would have a power rating and known amplifier. Powered subwoofers could be protected using the same mechanisms if the end user knows the subwoofers power limitations or the gain setting for a particular knob position.

Yet another embodiment a preconfigured surround sound package that includes the processor and speakers can be sold with all the speaker parameters configured in the system.

Yet in other embodiments a microphone based calibration can be utilized by the end user instead of having to enter any parameters. In these embodiments the user only has to position the microphone in the primary listening position and initiate the calibration process.

In this description various functions and operations may be encoded and performed by a hardware processor e.g. a microprocessor. Alternatively or in combination the functions and operations can be implemented using special purpose circuitry with or without software instructions such as using Application Specific Integrated Circuit ASIC or Field Programmable Gate Array FPGA . Embodiments can be implemented using hardwired circuitry without software instructions or in combination with software instructions. Thus the techniques are limited neither to any specific combination of hardware circuitry and software nor to any particular source for the instructions executed by the data processing system.

At least some aspects disclosed can be embodied at least in part in physically tangible firmware. That is the techniques may be carried out in a computer system or other data processing system in response to its processor such as a microprocessor executing sequences of instructions contained in a memory such as ROM volatile RAM non volatile memory cache or a remote storage device.

Alternate embodiments may be devised without departing from the spirit or the scope of the invention. For example the present invention is not limited to specific sound systems e.g. surround sound systems and could be used in other applications including speakers under rated for the given amplifier power rating or applications that require the use of a mixture of speakers of different sizes.

