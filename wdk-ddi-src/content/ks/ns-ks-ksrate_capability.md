---
UID: NS:ks.__unnamed_struct_57
title: KSRATE_CAPABILITY (ks.h)
description: The client uses the KSRATE_CAPABILITY structure in a KSPROPERTY_STREAM_RATECAPABILITY property request.
old-location: stream\ksrate_capability.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSRATE_CAPABILITY structure"]
ms.keywords: "*PKSRATE_CAPABILITY, KSRATE_CAPABILITY, KSRATE_CAPABILITY structure [Streaming Media Devices], PKSRATE_CAPABILITY, PKSRATE_CAPABILITY structure pointer [Streaming Media Devices], ks-struct_4697e3ed-7ef5-4278-be5f-96083d755ab0.xml, ks/KSRATE_CAPABILITY, ks/PKSRATE_CAPABILITY, stream.ksrate_capability"
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
req.typenames: KSRATE_CAPABILITY, *PKSRATE_CAPABILITY
f1_keywords:
 - PKSRATE_CAPABILITY
 - ks/PKSRATE_CAPABILITY
 - KSRATE_CAPABILITY
 - ks/KSRATE_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSRATE_CAPABILITY
---

# KSRATE_CAPABILITY structure


## -description

The client uses the KSRATE_CAPABILITY structure in a <a href="/windows-hardware/drivers/stream/ksproperty-stream-ratecapability">KSPROPERTY_STREAM_RATECAPABILITY</a> property request.

## -struct-fields

### -field Property

A structure of type <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> that specifies the property identifier.

### -field Rate

A structure of type <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksrate">KSRATE</a> that specifies the requested rate.
