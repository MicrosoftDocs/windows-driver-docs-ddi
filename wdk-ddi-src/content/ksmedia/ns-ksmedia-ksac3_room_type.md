---
UID: NS:ksmedia.__unnamed_struct_73
title: KSAC3_ROOM_TYPE (ksmedia.h)
description: The KSAC3_ROOM_TYPE structure specifies the type of audio mixing room in which an AC-3-encoded stream was produced.
old-location: audio\ksac3_room_type.htm
tech.root: audio
ms.assetid: adf514e1-5413-4552-b676-7567e8fa9954
ms.date: 04/30/2019
ms.keywords: "*PKSAC3_ROOM_TYPE, KSAC3_ROOM_TYPE, KSAC3_ROOM_TYPE structure [Audio Devices], PKSAC3_ROOM_TYPE, PKSAC3_ROOM_TYPE structure pointer [Audio Devices], aud-prop_cfc30aae-0335-42d9-bd6d-7888fed060af.xml, audio.ksac3_room_type, ksmedia/KSAC3_ROOM_TYPE, ksmedia/PKSAC3_ROOM_TYPE"
f1_keywords:
 - "ksmedia/KSAC3_ROOM_TYPE"
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
- KSAC3_ROOM_TYPE
product:
- Windows
targetos: Windows
req.typenames: KSAC3_ROOM_TYPE, *PKSAC3_ROOM_TYPE
---

# KSAC3_ROOM_TYPE structure


## -description


The KSAC3_ROOM_TYPE structure specifies the type of audio mixing room in which an AC-3-encoded stream was produced.


## -struct-fields




### -field fLargeRoom

Specifies the type and calibration of the mixing room used for the final audio mixing session. If <b>TRUE</b>, a large room with an X curve (described in the AC-3 specification; for more information, see the following Remarks section) was used. If <b>FALSE</b>, a small room with a flat curve was used.


## -remarks



This structure characterizes the production environment of an AC-3-encoded stream. The information in the structure is not typically used by the decoder, but might be used by other audio components after decoding.

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-ac3-room-type">KSPROPERTY_AC3_ROOM_TYPE</a> property.

For more information about room types, see the AC-3 specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-ac3-room-type">KSPROPERTY_AC3_ROOM_TYPE</a>
 

 

