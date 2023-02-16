---
UID: NS:ks.KSPROPERTY_MEDIAAVAILABLE
title: KSPROPERTY_MEDIAAVAILABLE (ks.h)
description: The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter.
old-location: stream\ksproperty_mediaavailable.htm
tech.root: stream
ms.date: 08/09/2021
keywords: ["KSPROPERTY_MEDIAAVAILABLE structure"]
ms.keywords: "*PKSPROPERTY_MEDIAAVAILABLE, KSPROPERTY_MEDIAAVAILABLE, KSPROPERTY_MEDIAAVAILABLE structure [Streaming Media Devices], PKSPROPERTY_MEDIAAVAILABLE, PKSPROPERTY_MEDIAAVAILABLE structure pointer [Streaming Media Devices], ks-struct_bb14a2ee-bf9b-4a73-ae35-967aea3d7086.xml, ks/KSPROPERTY_MEDIAAVAILABLE, ks/PKSPROPERTY_MEDIAAVAILABLE, stream.ksproperty_mediaavailable"
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
req.typenames: KSPROPERTY_MEDIAAVAILABLE, *PKSPROPERTY_MEDIAAVAILABLE
f1_keywords:
 - PKSPROPERTY_MEDIAAVAILABLE
 - ks/PKSPROPERTY_MEDIAAVAILABLE
 - KSPROPERTY_MEDIAAVAILABLE
 - ks/KSPROPERTY_MEDIAAVAILABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSPROPERTY_MEDIAAVAILABLE
 - KSPROPERTY_MEDIAAVAILABLE
---

# KSPROPERTY_MEDIAAVAILABLE structure


## -description

The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter. KSPROPERTY_MEDIAAVAILABLE is used in conjunction with the [KSPROPERTY_MEDIASEEKING_AVAILABLE](/windows-hardware/drivers/stream/ksproperty-mediaseeking-available) property request.

## -struct-fields

### -field Earliest

Pointer to a variable that receives the earliest time for efficient seeking.

### -field Latest

Pointer to a variable that receives the latest time for efficient seeking.

## -remarks

This structure corresponds with DirectShow's **IMediaSeeking::GetAvailable**.

## -see-also

[KSPROPERTY_MEDIASEEKING_AVAILABLE](/windows-hardware/drivers/stream/ksproperty-mediaseeking-available)

