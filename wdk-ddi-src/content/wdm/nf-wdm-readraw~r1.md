---
UID: NF:wdm.ReadRaw~r1
tech.root: kernel
title: ReadRaw
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw read operation on a volatile LONG value without any memory ordering or atomicity semantics.
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
 - ReadRaw
f1_keywords:
 - ReadRaw
 - wdm/ReadRaw
dev_langs:
 - c++
helpviewer_keywords:
 - ReadRaw
---

## -description

**ReadRaw** performs a raw read operation on a volatile LONG value without any memory ordering semantics.

## -parameters

### -param Source

[in] A pointer to a volatile LONG value to read from.

## -returns

Returns the LONG value read from the specified memory location.

## -remarks

The **ReadRaw** function executes a plain read from memory without providing any ordering, fencing, or atomicity guarantees. Use this function only when you knowingly manage synchronization elsewhere or when interacting with hardware where the raw access is required.

## -see-also

[**WriteRaw**](nf-wdm-writeraw~r1.md)
