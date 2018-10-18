---
UID: NS:ksmedia.KSRTAUDIO_HWREGISTER
title: KSRTAUDIO_HWREGISTER
author: windows-driver-content
description: The KSRTAUDIO_HWREGISTER structure specifies the address and additional information about a hardware register requested by the client.
old-location: audio\ksrtaudio_hwregister.htm
tech.root: audio
ms.assetid: 3d1dc600-f7cb-488e-9f92-678e0a6a58f8
ms.date: 5/8/2018
ms.keywords: "*PKSRTAUDIO_HWREGISTER, KSRTAUDIO_HWREGISTER, KSRTAUDIO_HWREGISTER structure [Audio Devices], PKSRTAUDIO_HWREGISTER, PKSRTAUDIO_HWREGISTER structure pointer [Audio Devices], aud-prop_f94f5b72-e081-48ee-96b9-4649201743d5.xml, audio.ksrtaudio_hwregister, ksmedia/KSRTAUDIO_HWREGISTER, ksmedia/PKSRTAUDIO_HWREGISTER"
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSRTAUDIO_HWREGISTER
product:
- Windows
targetos: Windows
req.typenames: KSRTAUDIO_HWREGISTER, *PKSRTAUDIO_HWREGISTER
---

# KSRTAUDIO_HWREGISTER structure


## -description


The KSRTAUDIO_HWREGISTER structure specifies the address and additional information about a hardware register requested by the client.  It is filled in by the driver in response to a register request via <a href="https://msdn.microsoft.com/library/windows/hardware/ff537381">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537376">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>.


## -struct-fields




### -field Register

Pointer to the register. This member specifies the virtual address into which the register is mapped.


### -field Width

Specifies the width, in bits, of the register. The value of this member can be 32 or 64.


### -field Numerator

Specifies the numerator of the frequency at which the clock register increments. See the following Remarks. section.


### -field Denominator

Specifies the denominator of the frequency at which the clock register increments. See the following Remarks. section.


### -field Accuracy

Specifies the accuracy of the clock or position register. See the following Remarks section.


## -remarks



For hardware position register requests via KSPROPERTY_RTAUDIO_POSITIONREGISTER the driver fills in the <b>Register</b>, <b>Width</b> and <b>Accuracy</b> members, because the other members are specific to clock registers.  For hardware clock register requests via KSPROPERTY_RTAUDIO_CLOCKREGISTER the driver fills in the entire structure.

A clock register is a counter that increments at the frequency of the internal hardware clock that drives the internal bus of the audio device. The register increments by one with each tick of the clock. The register begins counting when the device powers on and continues to run until the device powers off. The clock register is used by software to synchronize two or more devices with independent hardware clocks.

Members <b>Numerator</b> and <b>Denominator</b> together specify the frequency at which the clock register increments. The frequency is calculated by dividing <b>Numerator</b> by <b>Denominator</b>.

The clock register increments at the frequency of the internal clock of the audio device. This is the frequency that the audio device typically uses to clock events on its internal bus or on the external codec link. The hardware derives the audio sample frequencies by dividing down the internal clock frequency.

The audio device can derive its internal clock from an on-chip crystal oscillator or an external clock signal. For example, if a device derives a 16.5-MHz internal clock by dividing a 33-MHz external clock by two, the numerator and denominator can be specified as 33,000,000 and 2, respectively.

The <i>Accuracy</i> parameter specifies the maximum error in a position or clock register reading.  This is essentially a representation of the update rate for the register.  For clock registers the <i>Accuracy</i> parameter indicates the number of clock ticks between register updates.  In the preceding example of a 16.5-MHz internal clock, if the clock register is updated every 4 clocks, the <i>Accuracy</i> parameter would be set to 4 because the register needs to represent the accuracy of the clock register in units of clock ticks.  

For position registers, the <i>Accuracy</i> parameter represents the accuracy of the position register in units of bytes.  For example, the audio frame size for a 2-channel, 16-bit PCM stream is 4 bytes. If the position register increments (by two times the frame size) once every second tick of the sample clock, the accuracy value is 8 bytes. If the position register increments (by four times the frame size) once every fourth tick of the sample clock, the accuracy value is 16 bytes, and so on.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537376">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537381">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537498">KSRTAUDIO_HWREGISTER_PROPERTY</a>
 

 

