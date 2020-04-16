---
UID: NF:ks.KSEVENT_ITEM_IRP_STORAGE
title: KSEVENT_ITEM_IRP_STORAGE macro (ks.h)
description: This macro retrieves a pointer to the KSEVENT_ITEM structure stored in Irp.
old-location: stream\ksevent_item_irp_storage.htm
tech.root: stream
ms.assetid: c23fc5f4-2546-4330-bcdd-8fef59c8219a
ms.date: 04/23/2018
keywords: ["KSEVENT_ITEM_IRP_STORAGE macro"]
ms.keywords: KSEVENT_ITEM_IRP_STORAGE, KSEVENT_ITEM_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_ITEM_IRP_STORAGE, ksfunc_dc3f2f9e-fe47-46ac-9f51-9d07b42e5daf.xml, stream.ksevent_item_irp_storage
f1_keywords:
 - "ks/KSEVENT_ITEM_IRP_STORAGE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSEVENT_ITEM_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# KSEVENT_ITEM_IRP_STORAGE macro

## -description

This macro retrieves a pointer to the [KSEVENT_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item) structure stored in *Irp*.

## -parameters

### -param Irp

Contains a pointer to a KSEVENT_ITEM structure.

The macro is defined as follows:

```cpp
#define KSMETHOD_ITEM_IRP_STORAGE(Irp)  (*(const KSMETHOD_ITEM**)&(Irp)->Tail.Overlay.DriverContext[3])
```
