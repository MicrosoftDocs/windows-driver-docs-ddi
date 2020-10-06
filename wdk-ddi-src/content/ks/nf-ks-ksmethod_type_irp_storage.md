---
UID: NF:ks.KSMETHOD_TYPE_IRP_STORAGE
title: KSMETHOD_TYPE_IRP_STORAGE macro (ks.h)
description: This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact.
old-location: stream\ksmethod_type_irp_storage.htm
tech.root: stream
ms.assetid: f5327cbf-e71b-4c1c-94c0-0e27afb4d7cf
ms.date: 04/23/2018
keywords: ["KSMETHOD_TYPE_IRP_STORAGE macro"]
ms.keywords: KSMETHOD_TYPE_IRP_STORAGE, KSMETHOD_TYPE_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_TYPE_IRP_STORAGE, ksfunc_de99d882-5298-4972-9d16-fa4478d6229c.xml, stream.ksmethod_type_irp_storage
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
 - KSMETHOD_TYPE_IRP_STORAGE
 - ks/KSMETHOD_TYPE_IRP_STORAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSMETHOD_TYPE_IRP_STORAGE
---

# KSMETHOD_TYPE_IRP_STORAGE macro


## -description

This macro accesses the type of method as described in the [KSMETHOD_ITEM](./ns-ks-ksmethod_item.md). If the method will be processed asynchronously using [KsDispatchSpecificMethod](./nf-ks-ksdispatchspecificmethod.md), this storage must be maintained intact.

## -parameters

### -param Irp 

[in]
Specifies the IRP passed to the handler routine.

## -remarks

The relevant KSMETHOD_ITEM structure is extracted from **Irp->Tail.Overlay.DriverContext**. Parameters in **DriverContext** are initialized by [KsMethodHandler](./nf-ks-ksmethodhandler.md) and [KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md).

The macro is defined as follows:

```cpp
#define KSMETHOD_TYPE_IRP_STORAGE(Irp)  (*(ULONG_PTR*)(&(Irp)->Tail.Overlay.DriverContext[2]))
```

## -see-also

[KSMETHOD](/previous-versions/ff563398(v=vs.85))

[KSMETHOD_ITEM](./ns-ks-ksmethod_item.md)

[KSMETHOD_SET](./ns-ks-ksmethod_set.md)

[KsFastMethodHandler](./nf-ks-ksfastmethodhandler.md)

[KsMethodHandler](./nf-ks-ksmethodhandler.md)

[KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md)