---
UID: NF:portcls.IDrmPort.ForwardContentToFileObject
title: IDrmPort::ForwardContentToFileObject
description: The ForwardContentToFileObject method is obsolete and is maintained only to support existing drivers. 
tech.root: audio
ms.assetid: 74e03ac6-5a4a-431b-b395-6410c775bec5
ms.author: windowsdriverdev
ms.date: 10/31/2018
ms.topic: method
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
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IDrmPort.ForwardContentToFileObject
product: 
 - Windows
targetos: Windows

---

# IDrmPort::ForwardContentToFileObject


## -description

The ForwardContentToFileObject method is obsolete and is maintained only to support existing drivers. Note that this method is identical in operation to the [DrmForwardContentToFileObject](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttofileobject) function, and its parameter definitions and return value are also identical.


## -parameters

### -param ContentId



### -param FileObject



## -returns
This method returns NTSTATUS.
## -remarks

See comments in [DrmForwardContentToFileObject](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttofileobject).

## -see-also

[IDrmPort](nn-portcls-idrmport.md)
