---
UID: NF:ks.KsQueryObjectAccessMask
title: KsQueryObjectAccessMask function (ks.h)
description: The KsQueryObjectAccessMask function returns the access originally granted to the first client that created a handle on the associated object. Access cannot be changed by duplicating handles.
old-location: stream\ksqueryobjectaccessmask.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsQueryObjectAccessMask function"]
ms.keywords: KsQueryObjectAccessMask, KsQueryObjectAccessMask function [Streaming Media Devices], ks/KsQueryObjectAccessMask, ksfunc_f79d4971-874e-4efd-ab73-d88cdd573991.xml, stream.ksqueryobjectaccessmask
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsQueryObjectAccessMask
 - ks/KsQueryObjectAccessMask
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsQueryObjectAccessMask
---

# KsQueryObjectAccessMask function


## -description

The <b>KsQueryObjectAccessMask</b> function returns the access originally granted to the first client that created a handle on the associated object. Access cannot be changed by duplicating handles.

## -parameters

### -param Header [in]


Points to a header previously allocated by <b>KsAllocateObjectHeader</b> whose access-granted mask pointer is to be returned.

## -returns

The <b>KsQueryObjectAccessMask</b> function returns an access mask.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectheader">KsAllocateObjectHeader</a>
