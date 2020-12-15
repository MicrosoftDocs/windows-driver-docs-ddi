---
UID: NF:ks.KSMETHOD_ITEM_IRP_STORAGE
title: KSMETHOD_ITEM_IRP_STORAGE macro (ks.h)
description: This macro accesses a pointer to the relevant KSMETHOD_ITEM. Note that this pointer is only set when using KsMethodHandlerWithAllocator.
old-location: stream\ksmethod_item_irp_storage.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSMETHOD_ITEM_IRP_STORAGE macro"]
ms.keywords: KSMETHOD_ITEM_IRP_STORAGE, KSMETHOD_ITEM_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_ITEM_IRP_STORAGE, ksfunc_f9a51af4-aa4e-432d-99e3-03052e99b902.xml, stream.ksmethod_item_irp_storage
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
ms.custom: 19H1
f1_keywords:
 - KSMETHOD_ITEM_IRP_STORAGE
 - ks/KSMETHOD_ITEM_IRP_STORAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSMETHOD_ITEM_IRP_STORAGE
---

# KSMETHOD_ITEM_IRP_STORAGE macro


## -description

This macro accesses a pointer to the relevant [KSMETHOD_ITEM](./ns-ks-ksmethod_item.md). Note that this pointer is only set when using [KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md).

## -parameters

### -param Irp 

[in]
Specifies the IRP passed to the handler routine.

## -remarks

The pointer to a KSMETHOD_ITEM structure is extracted from `Irp->Tail.Overlay.DriverContext`. Parameters in **DriverContext** are initialized by [KsMethodHandler](./nf-ks-ksmethodhandler.md) and [KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md).

The macro is defined as follows:

```cpp
#define KSMETHOD_ITEM_IRP_STORAGE(Irp)  (*(const KSMETHOD_ITEM**)&(Irp)->;Tail.Overlay.DriverContext[3])
```

## -see-also

[KSMETHOD](/previous-versions/ff563398(v=vs.85))

[KSMETHOD_ITEM](./ns-ks-ksmethod_item.md)

[KSMETHOD_SET](./ns-ks-ksmethod_set.md)

[KsFastMethodHandler](./nf-ks-ksfastmethodhandler.md)

[KsMethodHandler](./nf-ks-ksmethodhandler.md)

[KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md)
