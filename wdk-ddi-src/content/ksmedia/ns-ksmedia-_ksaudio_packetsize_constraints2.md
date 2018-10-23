---
UID: NS:ksmedia._KSAUDIO_PACKETSIZE_CONSTRAINTS2
title: "_KSAUDIO_PACKETSIZE_CONSTRAINTS2"
author: windows-driver-content
description: The KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure describes the physical hardware constraints.
old-location: audio\ksaudio_packetsize_constraints2.htm
tech.root: audio
ms.assetid: E87C7AA7-A48A-4569-ADD5-9DC143F919B6
ms.date: 05/08/2018
ms.keywords: FILE_128_BYTE_ALIGNMENT, FILE_256_BYTE_ALIGNMENT, FILE_32_BYTE_ALIGNMENT, FILE_512_BYTE_ALIGNMENT, FILE_64_BYTE_ALIGNMENT, FILE_BYTE_ALIGNMENT, FILE_LONG_ALIGNMENT, FILE_OCTA_ALIGNMENT, FILE_QUAD_ALIGNMENT, FILE_WORD_ALIGNMENT, KSAUDIO_PACKETSIZE_CONSTRAINTS2, KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure [Audio Devices], PKSAUDIO_PACKETSIZE_CONSTRAINTS2, PKSAUDIO_PACKETSIZE_CONSTRAINTS2 structure pointer [Audio Devices], _KSAUDIO_PACKETSIZE_CONSTRAINTS2, audio.ksaudio_packetsize_constraints2, ksmedia/KSAUDIO_PACKETSIZE_CONSTRAINTS2, ksmedia/PKSAUDIO_PACKETSIZE_CONSTRAINTS2
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	KSAUDIO_PACKETSIZE_CONSTRAINTS2
product:
- Windows
targetos: Windows
req.typenames: KSAUDIO_PACKETSIZE_CONSTRAINTS2
---

# _KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure


## -description


The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS2</b> structure describes the physical hardware constraints. It includes an array of 0 or more <a href="https://msdn.microsoft.com/library/windows/hardware/dn965562">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a> structures describing constraints specific to any signal processing modes.
The driver sets this property before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537731">PcRegisterSubdevice</a> or otherwise enabling its KS filter interface for its streaming pins.


## -struct-fields




### -field MinPacketPeriodInHns

The absolute minimum processing period supported by the driver expressed in hundred-nanosecond (HNS) units. This value can be 0 if the driver has no specific minimum processing period.


### -field PacketSizeFileAlignment

The byte size alignment requirement. Use one of these defined file alignment values:

<a id="FILE_BYTE_ALIGNMENT"></a>
<a id="file_byte_alignment"></a>


#### FILE_BYTE_ALIGNMENT

<a id="FILE_WORD_ALIGNMENT"></a>
<a id="file_word_alignment"></a>


#### FILE_WORD_ALIGNMENT

<a id="FILE_LONG_ALIGNMENT"></a>
<a id="file_long_alignment"></a>


#### FILE_LONG_ALIGNMENT

<a id="FILE_QUAD_ALIGNMENT"></a>
<a id="file_quad_alignment"></a>


#### FILE_QUAD_ALIGNMENT

<a id="FILE_OCTA_ALIGNMENT"></a>
<a id="file_octa_alignment"></a>


#### FILE_OCTA_ALIGNMENT

<a id="FILE_32_BYTE_ALIGNMENT"></a>
<a id="file_32_byte_alignment"></a>


#### FILE_32_BYTE_ALIGNMENT

<a id="FILE_64_BYTE_ALIGNMENT"></a>
<a id="file_64_byte_alignment"></a>


#### FILE_64_BYTE_ALIGNMENT

<a id="FILE_128_BYTE_ALIGNMENT"></a>
<a id="file_128_byte_alignment"></a>


#### FILE_128_BYTE_ALIGNMENT

<a id="FILE_256_BYTE_ALIGNMENT"></a>
<a id="file_256_byte_alignment"></a>


#### FILE_256_BYTE_ALIGNMENT

<a id="FILE_512_BYTE_ALIGNMENT"></a>
<a id="file_512_byte_alignment"></a>


#### FILE_512_BYTE_ALIGNMENT


### -field MaxPacketSizeInBytes

The absolute maximum packet size supported by the driver in bytes. This can be zero if the driver has no specific maximum packet size. This size should at least be large enough to support 10 ms buffer of any format supported by the pin. This size should also be greater or equal to MinPacketSize constraints. 



### -field NumProcessingModeConstraints

The number of additional constraints for specific processing modes. This value can be 0.


### -field ProcessingModeConstraints

An array of 0 or more processing mode constraints. 



## -remarks



The driver sets this variable length data structure as the value of the DEVPKEY_KsAudio_PacketSize_Constraints2 property on the PnP interface of the KS filter that has the streaming pins with the constraints. 


For WaveRT drivers, this data structure describes the constraints for a WaveRT packet. Several WaveRT packets (typically 2) are concatenated to form the WaveRT buffer.

The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS2</b> struct is available  beginning with Windows 10, version 1607.



