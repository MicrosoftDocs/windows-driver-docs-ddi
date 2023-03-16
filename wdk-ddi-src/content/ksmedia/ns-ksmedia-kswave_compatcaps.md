---
UID: NS:ksmedia.KSWAVE_COMPATCAPS
title: KSWAVE_COMPATCAPS (ksmedia.h)
description: The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device.
tech.root: stream
ms.date: 03/15/2023
keywords: ["KSWAVE_COMPATCAPS structure"]
ms.keywords: "*PKSWAVE_COMPATCAPS, KSWAVE_COMPATCAPS, KSWAVE_COMPATCAPS structure [Streaming Media Devices], PKSWAVE_COMPATCAPS, PKSWAVE_COMPATCAPS structure pointer [Streaming Media Devices], dvdref_496e945d-fb6d-47da-8668-4cb8f1b265e6.xml, ksmedia/KSWAVE_COMPATCAPS, ksmedia/PKSWAVE_COMPATCAPS, stream.kswave_compatcaps"
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
req.typenames: KSWAVE_COMPATCAPS, *PKSWAVE_COMPATCAPS
f1_keywords:
 - PKSWAVE_COMPATCAPS
 - ksmedia/PKSWAVE_COMPATCAPS
 - KSWAVE_COMPATCAPS
 - ksmedia/KSWAVE_COMPATCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSWAVE_COMPATCAPS
 - KSWAVE_COMPATCAPS
---

## -description

The **KSWAVE_COMPATCAPS** structure is used to describe the compatible capabilities of a device.

## -struct-fields

### -field ulDeviceType

Specifies the following flags:

| Flag | Meaning |
|---|---|
| KSWAVE_COMPATCAPS_INPUT | Indicates that the device accepts input. |
| KSWAVE_COMPATCAPS_OUTPUT | Indicates that the device produces output. |

## -remarks

This structure is used by the [KSPROPERTY_WAVE_COMPATIBLE_CAPABILITIES](/windows-hardware/drivers/stream/ksproperty-wave-compatible-capabilities) property.

## -see-also

[KSPROPERTY_WAVE_COMPATIBLE_CAPABILITIES](/windows-hardware/drivers/stream/ksproperty-wave-compatible-capabilities)
