---
UID: NS:ksmedia._KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT
title: _KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT (ksmedia.h)
description: The KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure describes the constraints specific to any signal processing mode.
old-location: audio\ksaudio_packetsize_processingmode_constraint.htm
tech.root: audio
ms.assetid: 0BC6A03C-CF6D-4F56-985E-933E87200DFE
ms.date: 05/08/2018
ms.keywords: KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT, KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT structure [Audio Devices], _KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT, audio.ksaudio_packetsize_processingmode_constraint, ksmedia/KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT
f1_keywords:
 - "ksmedia/KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT"
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
- KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT
product:
- Windows
targetos: Windows
req.typenames: KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT
---

# _KSAUDIO_PACKETSIZE_SIGNALPROCESSINGMODE_CONSTRAINT structure


## -description


The <b>KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</b> structure describes the constraints specific to any signal processing mode.


## -struct-fields




### -field ProcessingMode

The signal processing mode that this constraint applies to.


### -field SamplesPerProcessingPacket

The processing frame size for the processing mode, expressed in number of samples. If this value is 0, the constraint is expressed by the <b>ProcessingPacketDurationInHns</b> field.


### -field ProcessingPacketDurationInHns

The processing frame size for the processing mode, expressed in hundred-nanosecond (HNS) units. This field is ignored if <b>SamplesPerProcessingPacket</b> is nonzero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ksaudio_packetsize_constraints">KSAUDIO_PACKETSIZE_CONSTRAINTS</a>
 

 

