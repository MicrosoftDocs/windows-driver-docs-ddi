---
UID: NF:ks.KSEVENT_ENTRY_IRP_STORAGE
title: KSEVENT_ENTRY_IRP_STORAGE macro (ks.h)
description: This macro retrieves a pointer to the KSEVENT_ENTRY structure stored in Irp.
tech.root: stream
ms.date: 03/11/2022
keywords: ["KSEVENT_ENTRY_IRP_STORAGE macro"]
ms.keywords: KSEVENT_ENTRY_IRP_STORAGE, KSEVENT_ENTRY_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_ENTRY_IRP_STORAGE, ksfunc_174dded2-4521-4d4a-b7ab-13401da80e5b.xml, stream.ksevent_entry_irp_storage
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
 - KSEVENT_ENTRY_IRP_STORAGE
 - ks/KSEVENT_ENTRY_IRP_STORAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSEVENT_ENTRY_IRP_STORAGE
---

## -description

This macro retrieves a pointer to the [**KSEVENT_ENTRY**](ns-ks-_ksevent_entry.md) structure stored in *Irp*. This information is initialized only for enable requests; it is not initialized for basic support requests. If the event enable is to be handled asynchronously, this storage location must be maintained intact.

## -parameters

### -param Irp

Contains a pointer to a KSEVENT_ENT****RY structure.

## -remarks

The macro is defined as follows:

```cpp
#define KSEVENT_ENTRY_IRP_STORAGE(Irp)   (*(PKSEVENT_ENTRY*)&(Irp)->Tail.Overlay.DriverContext[0])
```
