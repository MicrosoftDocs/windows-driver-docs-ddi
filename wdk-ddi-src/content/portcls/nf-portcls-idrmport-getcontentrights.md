---
UID: NF:portcls.IDrmPort.GetContentRights
title: IDrmPort::GetContentRights (portcls.h)
description: The GetContentRights method retrieves the DRM content rights that are assigned to a stream that is identified by a content ID.
tech.root: audio
ms.assetid: 9d6ed9a9-9d5e-4af6-b9f8-49431ad7d854
ms.date: 02/20/2019
f1_keywords:
 - "portcls/IDrmPort.GetContentRights"
ms.keywords: IDrmPort::GetContentRights, GetContentRights, IDrmPort.GetContentRights, IDrmPort::GetContentRights, IDrmPort.GetContentRights
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
 - IDrmPort.GetContentRights
product: 
 - Windows
targetos: Windows

---

# IDrmPort::GetContentRights


## -description

The GetContentRights method retrieves the DRM content rights that are assigned to a stream that is identified by a content ID. Note that this method is identical in operation to the [DrmGetContentRights](https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmgetcontentrights) function, and its parameter definitions and return value are also identical.

## -parameters

### -param ContentId

Specifies the DRM content ID. This parameter identifies a KS audio stream.

### -param DrmRights

Specifies the DRM content rights that are assigned to the stream that is identified by ContentId. This parameter is a pointer to a DRMRIGHTS structure.


## -returns
This method returns NTSTATUS.

## -remarks

See comments in [DrmGetContentRights](https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmgetcontentrights).


## -see-also

[IDrmPort](nn-portcls-idrmport.md)
