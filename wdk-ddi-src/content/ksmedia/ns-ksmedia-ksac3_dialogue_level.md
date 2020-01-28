---
UID: NS:ksmedia.__unnamed_struct_72
title: KSAC3_DIALOGUE_LEVEL (ksmedia.h)
description: The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream.
old-location: audio\ksac3_dialogue_level.htm
tech.root: audio
ms.assetid: c29d5cbc-ddcc-42e9-ac2d-e442a489adfd
ms.date: 04/30/2019
ms.keywords: "*PKSAC3_DIALOGUE_LEVEL, KSAC3_DIALOGUE_LEVEL, KSAC3_DIALOGUE_LEVEL structure [Audio Devices], PKSAC3_DIALOGUE_LEVEL, PKSAC3_DIALOGUE_LEVEL structure pointer [Audio Devices], aud-prop_223d9fe5-3b60-46b4-a157-7ddab97a75f8.xml, audio.ksac3_dialogue_level, ksmedia/KSAC3_DIALOGUE_LEVEL, ksmedia/PKSAC3_DIALOGUE_LEVEL"
f1_keywords:
 - "ksmedia/KSAC3_DIALOGUE_LEVEL"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSAC3_DIALOGUE_LEVEL
product:
- Windows
targetos: Windows
req.typenames: KSAC3_DIALOGUE_LEVEL, *PKSAC3_DIALOGUE_LEVEL
---

# KSAC3_DIALOGUE_LEVEL structure


## -description


The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream.


## -struct-fields




### -field DialogueLevel

Specifies how far the average dialog level is below digital 100 percent. Valid values are 1 through 31. The values 1 through 31 are interpreted as -1 decibels through -31 decibels with respect to digital 100 percent.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-ac3-bit-stream-mode">KSPROPERTY_AC3_BIT_STREAM_MODE</a> property.

For more information about dialog levels, see the AC-3 specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-ac3-bit-stream-mode">KSPROPERTY_AC3_BIT_STREAM_MODE</a>
 

 

