---
UID: NF:portcls.IDrmPort.DestroyContent
title: IDrmPort::DestroyContent (portcls.h)
description: The DestroyContent method deletes a DRM content ID that was created by IDrmPort::CreateContentMixed.
tech.root: audio
ms.date: 02/20/2019
keywords: ["IDrmPort::DestroyContent"]
ms.keywords: IDrmPort::DestroyContent, DestroyContent, IDrmPort.DestroyContent, IDrmPort::DestroyContent, IDrmPort.DestroyContent
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IDrmPort::DestroyContent
 - portcls/IDrmPort::DestroyContent
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDrmPort::DestroyContent
---

# IDrmPort::DestroyContent


## -description

The DestroyContent method deletes a DRM content ID that was created by IDrmPort::CreateContentMixed. Note that this method is identical in operation to the [DrmDestroyContent](../drmk/nf-drmk-drmdestroycontent.md) function, and its parameter definitions and return value are also identical.

## -parameters

### -param ContentId

Specifies a nonzero DRM content ID assigned to a KS audio stream by DrmCreateContentMixed. Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.

## -returns

This method returns NTSTATUS - STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

See comments in [DrmDestroyContent](../drmk/nf-drmk-drmdestroycontent.md).

## -see-also

[IDrmPort](nn-portcls-idrmport.md)

