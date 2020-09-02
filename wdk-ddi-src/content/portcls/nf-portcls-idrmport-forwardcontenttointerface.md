---
UID: NF:portcls.IDrmPort.ForwardContentToInterface
title: IDrmPort::ForwardContentToInterface (portcls.h)
description: The ForwardContentToInterface method accepts a pointer to the COM interface of an object to which the caller intends to forward protected content.
tech.root: audio
ms.assetid: 8ccec5e2-2239-4d3d-a789-f7d1800966d7
ms.date: 02/20/2019
keywords: ["IDrmPort::ForwardContentToInterface"]
ms.keywords: IDrmPort::ForwardContentToInterface, ForwardContentToInterface, IDrmPort.ForwardContentToInterface, IDrmPort::ForwardContentToInterface, IDrmPort.ForwardContentToInterface
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
 - IDrmPort::ForwardContentToInterface
 - portcls/IDrmPort::ForwardContentToInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDrmPort.ForwardContentToInterface
product:
 - Windows
---

# IDrmPort::ForwardContentToInterface


## -description

The ForwardContentToInterface method accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. Note that this method is identical in operation to the [DrmForwardContentToInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface) function, and its parameter definitions and return value are also identical.

## -parameters

### -param ContentId

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.

### -param pUnknown

Pointer to a COM interface that directly receives KS audio stream data for a KS audio filter.

### -param NumMethods

Specifies the total number of methods in the COM interface that pUnknown points to, including all the methods in its base interfaces.

## -returns

This method returns NTSTATUS.

## -remarks

See comments in [DrmForwardContentToInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface).

## -see-also

[IDrmPort](nn-portcls-idrmport.md)

