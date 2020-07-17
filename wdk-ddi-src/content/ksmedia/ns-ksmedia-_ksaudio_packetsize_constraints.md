---
UID: NS:ksmedia._KSAUDIO_PACKETSIZE_CONSTRAINTS
title: _KSAUDIO_PACKETSIZE_CONSTRAINTS (ksmedia.h)
description: The KSAUDIO_PACKETSIZE_CONSTRAINTS structure describes the physical hardware constraints.
old-location: audio\ksaudio_packetsize_constraints.htm
tech.root: audio
ms.assetid: 6BD3E98A-A2A5-4285-8F41-1445F90DD8EB
ms.date: 05/08/2018
keywords: ["_KSAUDIO_PACKETSIZE_CONSTRAINTS structure"]
ms.keywords: FILE_128_BYTE_ALIGNMENT, FILE_256_BYTE_ALIGNMENT, FILE_32_BYTE_ALIGNMENT, FILE_512_BYTE_ALIGNMENT, FILE_64_BYTE_ALIGNMENT, FILE_BYTE_ALIGNMENT, FILE_LONG_ALIGNMENT, FILE_OCTA_ALIGNMENT, FILE_QUAD_ALIGNMENT, FILE_WORD_ALIGNMENT, KSAUDIO_PACKETSIZE_CONSTRAINTS, KSAUDIO_PACKETSIZE_CONSTRAINTS structure [Audio Devices], PKSAUDIO_PACKETSIZE_CONSTRAINTS, PKSAUDIO_PACKETSIZE_CONSTRAINTS structure pointer [Audio Devices], _KSAUDIO_PACKETSIZE_CONSTRAINTS, audio.ksaudio_packetsize_constraints, ksmedia/KSAUDIO_PACKETSIZE_CONSTRAINTS, ksmedia/PKSAUDIO_PACKETSIZE_CONSTRAINTS
f1_keywords:
 - "ksmedia/KSAUDIO_PACKETSIZE_CONSTRAINTS"
 - "KSAUDIO_PACKETSIZE_CONSTRAINTS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSAUDIO_PACKETSIZE_CONSTRAINTS
product:
- Windows
targetos: Windows
req.typenames: KSAUDIO_PACKETSIZE_CONSTRAINTS
---

# _KSAUDIO_PACKETSIZE_CONSTRAINTS structure


## -description


The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS</b> structure describes the physical hardware constraints. It includes an array of 0 or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a> structures describing constraints specific to any signal processing modes.
The driver sets this property before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a> or otherwise enabling its KS filter interface for its streaming pins.


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


### -field Reserved

Unused.


### -field NumProcessingModeConstraints

The number of additional constraints for specific processing modes. This value can be 0.


### -field ProcessingModeConstraints

An array of 0 or more processing mode constraints. 



## -remarks



The driver sets this variable length data structure as the value of the DEVPKEY_KsAudio_PacketSize_Constraints property on the PnP interface of the KS filter that has the streaming pins with the constraints. 


For WaveRT drivers, this data structure describes the constraints for a WaveRT packet. Several WaveRT packets (typically 2) are concatenated to form the WaveRT buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>
 

 

