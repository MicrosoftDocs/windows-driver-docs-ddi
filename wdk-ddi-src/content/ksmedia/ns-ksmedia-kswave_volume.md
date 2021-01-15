---
UID: NS:ksmedia.__unnamed_struct_53
title: KSWAVE_VOLUME (ksmedia.h)
description: The KSWAVE_VOLUME structure is used to describe sample volume.
old-location: stream\kswave_volume.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSWAVE_VOLUME structure"]
ms.keywords: "*PKSWAVE_VOLUME, KSWAVE_VOLUME, KSWAVE_VOLUME structure [Streaming Media Devices], PKSWAVE_VOLUME, PKSWAVE_VOLUME structure pointer [Streaming Media Devices], dvdref_602cb4a7-2e70-43a1-8e1a-7604d5b48bc1.xml, ksmedia/KSWAVE_VOLUME, ksmedia/PKSWAVE_VOLUME, stream.kswave_volume"
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
targetos: Windows
req.typenames: KSWAVE_VOLUME, *PKSWAVE_VOLUME
f1_keywords:
 - PKSWAVE_VOLUME
 - ksmedia/PKSWAVE_VOLUME
 - KSWAVE_VOLUME
 - ksmedia/KSWAVE_VOLUME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSWAVE_VOLUME
 - KSWAVE_VOLUME
---

# KSWAVE_VOLUME structure


## -description

The KSWAVE_VOLUME structure is used to describe sample volume.

## -struct-fields

### -field LeftAttenuation

Specifies the amount of left attenuation.

### -field RightAttenuation

Specifies the amount of right attenuation.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-wave-volume">KSPROPERTY_WAVE_VOLUME</a> property.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-wave-volume">KSPROPERTY_WAVE_VOLUME</a>

