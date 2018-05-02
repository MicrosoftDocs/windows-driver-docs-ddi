---
UID: NS:ksmedia.KSAUDIO_MIC_ARRAY_GEOMETRY
title: KSAUDIO_MIC_ARRAY_GEOMETRY
author: windows-driver-content
description: The KSAUDIO_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array.
old-location: audio\ksaudio_mic_array_geometry.htm
old-project: audio
ms.assetid: 49b8f602-8f82-4445-98f2-a63563689561
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PKSAUDIO_MIC_ARRAY_GEOMETRY, KSAUDIO_MIC_ARRAY_GEOMETRY, KSAUDIO_MIC_ARRAY_GEOMETRY structure [Audio Devices], PKSAUDIO_MIC_ARRAY_GEOMETRY, PKSAUDIO_MIC_ARRAY_GEOMETRY structure pointer [Audio Devices], aud-prop_b25763af-a8d5-4335-ae71-f3bc59218201.xml, audio.ksaudio_mic_array_geometry, ksmedia/KSAUDIO_MIC_ARRAY_GEOMETRY, ksmedia/PKSAUDIO_MIC_ARRAY_GEOMETRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	KSAUDIO_MIC_ARRAY_GEOMETRY
product:
- Windows
targetos: Windows
req.typenames: KSAUDIO_MIC_ARRAY_GEOMETRY, *PKSAUDIO_MIC_ARRAY_GEOMETRY
---

# KSAUDIO_MIC_ARRAY_GEOMETRY structure


## -description


The KSAUDIO_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array. The <b>usNumberOfMicrophones</b> member indicates the number of microphones in the physical array. The KsMicCoord member is a variable of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537086">KSAUDIO_MICROPHONE_COORDINATES</a> and it is an array of structures. The number of entries in this array is given by the value of the <b>usNumberOfMicrophones</b> member.


## -struct-fields




### -field usVersion

Specifies the version number of the KSAUDIO_MIC_ARRAY_GEOMETRY structure. This member is a BCD value and is currently set to 0x0100, which represents a version number of 1.0.


### -field usMicArrayType

Specifies the type of microphone array in use. This member can be any one of the KSMICARRAY_MICARRAYTYPE enumeration values shown in the following table.

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Microphone array type</b>

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICARRAYTYPE_LINEAR

</td>
<td>
Linear

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICARRAYTYPE_PLANAR

</td>
<td>
Planar

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICARRAYTYPE_3D

</td>
<td>
3D

</td>
</tr>
</table>
 


### -field wVerticalAngleBegin

Specifies the vertical angle of the start of the working volume of the microphone array.


### -field wVerticalAngleEnd

Specifies the vertical angle of the end of the working volume of the microphone array.


### -field wHorizontalAngleBegin

Work Volume HorizontalAngle Begin


### -field wHorizontalAngleEnd

Work Volume HorizontalAngle End


### -field usFrequencyBandLo

Specifies the low end of the frequency range for the microphone array.


### -field usFrequencyBandHi

Specifies the high end of the frequency range for the microphone array.


### -field usNumberOfMicrophones

Specifies the number of microphones in the microphone array.


### -field KsMicCoord

Specifies the array of KSAUDIO_MICROPHONE_COORDINATES structures that contains the locations of the microphones in the array.


## -remarks



All angle values are expressed in units of 1/10000th of a radian. For example, 3.1416 radians is expressed as 31416 units. Acceptable values range from -31416 to 31416 units.

All coordinate values are expressed in millimeters. Acceptable values range from -32768 to 32767, inclusive.

Frequency values are expressed in Hertz (Hz).

For more information about how to process a microphone array in Windows Vista, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=8751">Audio Technologies for Windows </a> page on the WHDC website and refer to the following white papers:

<a href="http://go.microsoft.com/fwlink/p/?linkid=120592">Microphone Array Support in Windows Vista</a>

<a href="http://go.microsoft.com/fwlink/p/?linkid=120593">How to Build and Use Microphone Arrays for Windows Vista</a>




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537086">KSAUDIO_MICROPHONE_COORDINATES</a>
 

 

