---
UID: NC:ks.PFNKSINTERSECTHANDLER
title: PFNKSINTERSECTHANDLER (ks.h)
description: A streaming minidriver's KStrIntersectHandler routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.
tech.root: stream
ms.date: 03/06/2023
keywords: ["PFNKSINTERSECTHANDLER callback function"]
ms.keywords: KStrIntersectHandler, KStrIntersectHandler routine [Streaming Media Devices], PFNKSINTERSECTHANDLER, ks/KStrIntersectHandler, ksfunc_25fa087e-9d66-4479-aa4c-632a63ee6779.xml, stream.kstrintersecthandler
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFNKSINTERSECTHANDLER
 - ks/PFNKSINTERSECTHANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSINTERSECTHANDLER
---

## -description

A streaming minidriver's *KStrIntersectHandler* routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.

## -parameters

### -param Irp [in]

Specifies the IRP that handles the property request.

### -param Pin [in]

Specifies the specific property being queried and the pin factory identifier that was validated.

### -param DataRange [in]

Specifies the current data range to compare. The data range has been validated as either matching a particular range on the pin or as a wildcard match.

### -param Data [out, optional]

Specifies the data format returned, or the size, in bytes, of the data format.

## -returns

Returns STATUS_SUCCESS if there is a data intersection that fits in the supplied buffer. Otherwise, one of the following values is returned.

| Return code | Description |
|---|---|
| **STATUS_BUFFER_OVERFLOW** | For successful size queries. |
| **STATUS_BUFFER_TOO_SMALL** | If the supplied buffer is too small. |
| **STATUS_NO_MATCH** | If there is no intersection. |

## -see-also

[KsPinDataIntersection](/windows-hardware/drivers/ddi/ks/nf-ks-kspindataintersection)
