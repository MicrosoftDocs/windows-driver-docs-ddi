---
UID: NF:portcls.IDrmPort.DestroyContent
title: IDrmPort::DestroyContent
author: windows-driver-content
description: The DestroyContent method deletes a DRM content ID that was created by IDrmPort::CreateContentMixed.
tech.root: audio
ms.assetid: f37f5dda-6223-41e5-bdfd-5ac8a66d0525
ms.author: windowsdriverdev
ms.date: 10/31/2018
ms.topic: method
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
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IDrmPort.DestroyContent
product: 
 - Windows
targetos: Windows

---

# IDrmPort::DestroyContent


## -description

The DestroyContent method deletes a DRM content ID that was created by IDrmPort::CreateContentMixed. Note that this method is identical in operation to the [DrmDestroyContent](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmdestroycontent) function, and its parameter definitions and return value are also identical.

## -parameters

### -param ContentId


## -returns
This method returns NTSTATUS.

## -remarks
See comments in [DrmDestroyContent](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmdestroycontent).

## -see-also

[IDrmPort](nn-portcls-idrmport.md)