---
UID: NS:ksmedia.KSRTAUDIO_HWREGISTER
title: KSRTAUDIO_HWREGISTER
author: windows-driver-content
description: The KSRTAUDIO_HWREGISTER structure specifies the address and additional information about a hardware register requested by the client.
old-location: audio\ksrtaudio_hwregister.htm
old-project: audio
ms.assetid: 3d1dc600-f7cb-488e-9f92-678e0a6a58f8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.ksrtaudio_hwregister, *PKSRTAUDIO_HWREGISTER, PKSRTAUDIO_HWREGISTER structure pointer [Audio Devices], aud-prop_f94f5b72-e081-48ee-96b9-4649201743d5.xml, PKSRTAUDIO_HWREGISTER, ksmedia/KSRTAUDIO_HWREGISTER, ksmedia/PKSRTAUDIO_HWREGISTER, KSRTAUDIO_HWREGISTER, KSRTAUDIO_HWREGISTER structure [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSRTAUDIO_HWREGISTER
product: Windows
targetos: Windows
req.typenames: "*PKSRTAUDIO_HWREGISTER, KSRTAUDIO_HWREGISTER"
---

# KSRTAUDIO_HWREGISTER structure


## -description


The KSRTAUDIO_HWREGISTER structure specifies the address and additional information about a hardware register requested by the client.  It is filled in by the driver in response to a register request via <a href="https://msdn.microsoft.com/library/windows/hardware/ff537381">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537376">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>.


## -syntax


````
typedef struct {
  PVOID     Register;
  ULONG     Width;
  ULONGLONG Numerator;
  ULONGLONG Denominator;
  ULONG     Accuracy;
} KSRTAUDIO_HWREGISTER, *PKSRTAUDIO_HWREGISTER;
````


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

<a href="..\ksmedia\ns-ksmedia-ksrtaudio_hwregister_property.md">KSRTAUDIO_HWREGISTER_PROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSRTAUDIO_HWREGISTER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

