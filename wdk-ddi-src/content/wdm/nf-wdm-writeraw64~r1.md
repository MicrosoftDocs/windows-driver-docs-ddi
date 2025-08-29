---
UID: NF:wdm.WriteRaw64~r1
tech.root: kernel
title: WriteRaw64
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw write operation to a volatile LONG64 value without any memory ordering or atomicity semantics.
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
 - WriteRaw64
f1_keywords:
 - WriteRaw64
 - wdm/WriteRaw64
dev_langs:
 - c++
helpviewer_keywords:
 - WriteRaw64
---

## -description

**WriteRaw64** performs a raw write operation to a volatile LONG64 value without any memory ordering or atomicity semantics.

## -parameters

### -param Destination

[out] A pointer to the volatile LONG64 variable to write to.

### -param Value

[in] The LONG64 value to write to the destination.

## -remarks

The **WriteRaw64** function performs a raw memory write operation on a 64-bit value without compiler optimization barriers or synchronization guarantees.

## -see-also

[ReadRaw64](nf-wdm-readraw64~r1.md)

[WriteRaw](nf-wdm-writeraw~r1.md)
