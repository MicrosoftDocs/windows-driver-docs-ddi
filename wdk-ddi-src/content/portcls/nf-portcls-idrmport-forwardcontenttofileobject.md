---
UID: NF:portcls.IDrmPort.ForwardContentToFileObject
title: IDrmPort::ForwardContentToFileObject (portcls.h)
description: The ForwardContentToFileObject method is obsolete and is maintained only to support existing drivers.
tech.root: audio
ms.date: 02/20/2019
keywords: ["IDrmPort::ForwardContentToFileObject"]
ms.keywords: IDrmPort::ForwardContentToFileObject, ForwardContentToFileObject, IDrmPort.ForwardContentToFileObject, IDrmPort::ForwardContentToFileObject, IDrmPort.ForwardContentToFileObject
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
 - IDrmPort::ForwardContentToFileObject
 - portcls/IDrmPort::ForwardContentToFileObject
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDrmPort::ForwardContentToFileObject
product:
 - Windows
---

# IDrmPort::ForwardContentToFileObject


## -description

The ForwardContentToFileObject method is obsolete and is maintained only to support existing drivers. Note that this method is identical in operation to the [DrmForwardContentToFileObject](../drmk/nf-drmk-drmforwardcontenttofileobject.md) function, and its parameter definitions and return value are also identical.

## -parameters

### -param ContentId

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.

### -param FileObject

Pointer to a file object that represents the KS audio pin to which the KS audio stream is sent.

## -returns

This method returns NTSTATUS - STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. STATUS_NOT_IMPLEMENTED indicates that the KS audio pin that is associated with FileObject does not support the DRM content rights that are assigned to ContentId.

## -remarks

See comments in [DrmForwardContentToFileObject](../drmk/nf-drmk-drmforwardcontenttofileobject.md).

## -see-also

[IDrmPort](nn-portcls-idrmport.md)

