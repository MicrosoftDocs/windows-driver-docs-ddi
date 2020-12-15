---
UID: NF:ks.KSEVENT_SET_IRP_STORAGE
title: KSEVENT_SET_IRP_STORAGE macro (ks.h)
description: This macro retrieves a pointer to the KSEVENT_SET structure stored in Irp. This information is initialized only for basic support requests; it is not initialized for enable requests.
old-location: stream\ksevent_set_irp_storage.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSEVENT_SET_IRP_STORAGE macro"]
ms.keywords: KSEVENT_SET_IRP_STORAGE, KSEVENT_SET_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_SET_IRP_STORAGE, ksfunc_d0511067-dd15-4e5d-9adf-acc73885a248.xml, stream.ksevent_set_irp_storage
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
 - KSEVENT_SET_IRP_STORAGE
 - ks/KSEVENT_SET_IRP_STORAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSEVENT_SET_IRP_STORAGE
---

# KSEVENT_SET_IRP_STORAGE macro


## -description

This macro retrieves a pointer to the [KSEVENT_SET](./ns-ks-ksevent_set.md) structure stored in *Irp*. This information is initialized only for basic support requests; it is not initialized for enable requests.

## -parameters

### -param Irp

Contains a pointer to a KSEVENT_SET structure.

The macro is defined as follows:

```cpp
#define KSMETHOD_SET_IRP_STORAGE(Irp)   (*(const KSMETHOD_SET**)&(Irp)->Tail.Overlay.DriverContext[0])
```
