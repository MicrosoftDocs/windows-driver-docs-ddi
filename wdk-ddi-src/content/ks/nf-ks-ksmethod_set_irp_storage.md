---
UID: NF:ks.KSMETHOD_SET_IRP_STORAGE
title: KSMETHOD_SET_IRP_STORAGE macro (ks.h)
description: This macro returns a pointer to the KSMETHOD_SET in which the method is located.
old-location: stream\ksmethod_set_irp_storage.htm
tech.root: stream
ms.assetid: bc0a309d-305e-400a-b571-7958926dd1dc
ms.date: 04/23/2018
ms.keywords: KSMETHOD_SET_IRP_STORAGE, KSMETHOD_SET_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_SET_IRP_STORAGE, ksfunc_d413bf2a-7d63-48c2-9e75-d84cf1344f5c.xml, stream.ksmethod_set_irp_storage
ms.topic: macro
f1_keywords:
 - "ks/KSMETHOD_SET_IRP_STORAGE"
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
- KSMETHOD_SET_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: 19H1
---

# KSMETHOD_SET_IRP_STORAGE macro

## -description

This macro returns a pointer to the [KSMETHOD_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_set) in which the method is located.

## -parameters

### -param Irp [in]

Specifies the IRP passed to the handler routine.

## -remarks

The pointer to a KSMETHOD_SET structure is extracted from `Irp->Tail.Overlay.DriverContext`. Parameters in **DriverContext** are initialized by [KsMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandler) and [KsMethodHandlerWithAllocator](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandlerwithallocator).

The macro is defined as follows:

```cpp
#define KSMETHOD_SET_IRP_STORAGE(Irp)   (*(const KSMETHOD_SET**)&(Irp)->Tail.Overlay.DriverContext[0])
```

## -see-also

[KSMETHOD](https://docs.microsoft.com/previous-versions/ff563398(v=vs.85))

[KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item)

[KSMETHOD_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_set)

[KsFastMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfastmethodhandler)

[KsMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandler)

[KsMethodHandlerWithAllocator](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandlerwithallocator)
