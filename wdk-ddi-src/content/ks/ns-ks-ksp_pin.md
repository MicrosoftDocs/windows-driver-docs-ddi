---
UID: NS:ks.KSP_PIN
title: KSP_PIN (ks.h)
description: Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSP_PIN structure"]
ms.keywords: "*PKSP_PIN, KSPROPERTY_PIN_FLAGS_ATTRIBUTE_RANGE_AWARE, KSP_PIN, KSP_PIN structure [Streaming Media Devices], PKSP_PIN, PKSP_PIN structure pointer [Streaming Media Devices], ks-struct_02faf16f-fb8d-4f1f-9176-e2c379a36d4e.xml, ks/KSP_PIN, ks/PKSP_PIN, stream.ksp_pin"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSP_PIN, *PKSP_PIN
f1_keywords:
 - PKSP_PIN
 - ks/PKSP_PIN
 - KSP_PIN
 - ks/KSP_PIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSP_PIN
 - KSP_PIN
---

## -description

Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request.

## -struct-fields

### -field Property

Specifies a [**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure) structure.

### -field PinId

Specifies the pin type ID.

### -field Reserved

Reserved. Should be set to zero.

Reserved. Should be set to zero.

### -field Flags

Pin flags. This is set to either 0 or the following.

| Value | Description |
|---|---|
| **KSPROPERTY_PIN_FLAGS_ATTRIBUTE_RANGE_AWARE** | The client is aware of attributes and handles attribute ranges. |

## -see-also

[**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure)
