---
UID: NF:wdm.WriteRaw~r1
tech.root: kernel
title: WriteRaw
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw write operation to a volatile LONG value without any memory ordering or atomicity semantics.
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
 - WriteRaw
f1_keywords:
 - WriteRaw
 - wdm/WriteRaw
dev_langs:
 - c++
helpviewer_keywords:
 - WriteRaw
---

## -description

**WriteRaw** performs a raw write operation to a volatile LONG value without any memory ordering or atomicity semantics.

## -parameters

### -param Destination

[out] A pointer to the volatile LONG variable to write to.

### -param Value

[in] The LONG value to write to the destination.

## -remarks

The **WriteRaw** function performs a raw memory write operation without compiler optimization barriers or synchronization guarantees.

## -see-also

[ReadRaw](nf-wdm-readraw~r1.md)
