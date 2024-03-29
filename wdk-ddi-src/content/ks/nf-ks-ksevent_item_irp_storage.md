---
UID: NF:ks.KSEVENT_ITEM_IRP_STORAGE
title: KSEVENT_ITEM_IRP_STORAGE macro (ks.h)
description: This macro retrieves a pointer to the KSEVENT_ITEM structure stored in Irp.
tech.root: stream
ms.date: 03/11/2022
keywords: ["KSEVENT_ITEM_IRP_STORAGE macro"]
ms.keywords: KSEVENT_ITEM_IRP_STORAGE, KSEVENT_ITEM_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_ITEM_IRP_STORAGE, ksfunc_dc3f2f9e-fe47-46ac-9f51-9d07b42e5daf.xml, stream.ksevent_item_irp_storage
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
 - KSEVENT_ITEM_IRP_STORAGE
 - ks/KSEVENT_ITEM_IRP_STORAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSEVENT_ITEM_IRP_STORAGE
---

## -description

This macro retrieves a pointer to the [**KSEVENT_ITEM**](ns-ks-ksevent_item.md) structure stored in *Irp*.

## -parameters

### -param Irp

Contains a pointer to a **KSEVENT_ITEM** structure.

## -remarks

The macro is defined as follows:

```cpp
#define KSMETHOD_ITEM_IRP_STORAGE(Irp)  (*(const KSMETHOD_ITEM**)&(Irp)->Tail.Overlay.DriverContext[3])
```
