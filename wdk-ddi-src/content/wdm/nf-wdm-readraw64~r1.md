---
UID: NF:wdm.ReadRaw64~r1
tech.root: kernel
title: ReadRaw64
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw read operation on a volatile LONG64 value without any memory ordering or atomicity semantics.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ReadRaw64
f1_keywords:
 - ReadRaw64
 - wdm/ReadRaw64
dev_langs:
 - c++
helpviewer_keywords:
 - ReadRaw64
---

## -description

**ReadRaw64** performs a raw read operation on a volatile LONG64 value without any memory ordering or atomicity semantics.

## -parameters

### -param Source

[in] A pointer to the volatile LONG64 variable to read from.

## -returns

Returns the LONG64 value read from the specified memory location.

## -remarks

The **ReadRaw64** function performs a raw memory read operation on a 64-bit value without compiler optimization barriers or synchronization guarantees.

## -see-also

[ReadAcquire64](nf-wdm-readacquire64.md)

[ReadNoFence64](nf-wdm-readnofence64.md)

[WriteRaw64](nf-wdm-writeraw64~r1.md)

[ReadRaw](nf-wdm-readraw~r1.md)
