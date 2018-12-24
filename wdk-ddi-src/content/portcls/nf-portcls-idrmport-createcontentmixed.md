---
UID: NF:portcls.IDrmPort.CreateContentMixed
title: IDrmPort::CreateContentMixed
description: The CreateContentMixed method computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams. 
tech.root: audio
ms.assetid: 26ea9bd4-5540-4be7-bf34-8a56e2812ccd
ms.author: windowsdriverdev
ms.date: 10/31/2018
ms.topic: method
ms.keywords: IDrmPort::CreateContentMixed, CreateContentMixed, IDrmPort.CreateContentMixed, IDrmPort::CreateContentMixed, IDrmPort.CreateContentMixed
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
 - IDrmPort.CreateContentMixed
product: 
 - Windows
targetos: Windows

---

# IDrmPort::CreateContentMixed


## -description

The CreateContentMixed method computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams. Note that this method is identical in operation to the [DrmCreateContentMixed function](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmcreatecontentmixed), and its parameter definitions and return value are also identical.

## -parameters

### -param paContentId



### -param cContentId



### -param pMixedContentId




## -returns
This method returns NTSTATUS.
## -remarks

## -see-also

[IDrmPort](nn-portcls-idrmport.md)
