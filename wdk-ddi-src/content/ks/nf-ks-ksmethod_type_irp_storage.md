---
UID: NF:ks.KSMETHOD_TYPE_IRP_STORAGE
title: KSMETHOD_TYPE_IRP_STORAGE macro (ks.h)
description: This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact.
old-location: stream\ksmethod_type_irp_storage.htm
tech.root: stream
ms.assetid: f5327cbf-e71b-4c1c-94c0-0e27afb4d7cf
ms.date: 04/23/2018
ms.keywords: KSMETHOD_TYPE_IRP_STORAGE, KSMETHOD_TYPE_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_TYPE_IRP_STORAGE, ksfunc_de99d882-5298-4972-9d16-fa4478d6229c.xml, stream.ksmethod_type_irp_storage
ms.topic: macro
f1_keywords:
 - "ks/KSMETHOD_TYPE_IRP_STORAGE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSMETHOD_TYPE_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# KSMETHOD_TYPE_IRP_STORAGE macro

## -description

This macro accesses the type of method as described in the [KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmethod_item). If the method will be processed asynchronously using [KsDispatchSpecificMethod](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksdispatchspecificmethod), this storage must be maintained intact.

## -parameters

### -param Irp [in]

Specifies the IRP passed to the handler routine.

## -remarks

The relevant KSMETHOD_ITEM structure is extracted from **Irp->Tail.Overlay.DriverContext**. Parameters in **DriverContext** are initialized by [KsMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksmethodhandler) and [KsMethodHandlerWithAllocator](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksmethodhandlerwithallocator).

The macro is defined as follows:

```cpp
#define KSMETHOD_TYPE_IRP_STORAGE(Irp)  (*(ULONG_PTR*)(&(Irp)->Tail.Overlay.DriverContext[2]))
```

## -see-also

[KSMETHOD](https://docs.microsoft.com/previous-versions/ff563398(v=vs.85))

[KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmethod_item)

[KSMETHOD_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmethod_set)

[KsFastMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfastmethodhandler)

[KsMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksmethodhandler)

[KsMethodHandlerWithAllocator](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksmethodhandlerwithallocator)
