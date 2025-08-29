---
UID: NF:wdm.ReadRaw8~r1
tech.root: kernel
title: ReadRaw8
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw read operation on a volatile CHAR value without any memory ordering or atomicity semantics.
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
 - ReadRaw8
f1_keywords:
 - ReadRaw8
 - wdm/ReadRaw8
dev_langs:
 - c++
helpviewer_keywords:
 - ReadRaw8
---

## -description

**ReadRaw8** performs a raw read operation on a volatile CHAR value without any memory ordering or atomicity semantics.

## -parameters

### -param Source

[in] A pointer to the volatile CHAR variable to read from.

## -returns

Returns the CHAR value read from the specified memory location.

## -remarks

The **ReadRaw8** function performs a raw memory read operation on an 8-bit value without compiler optimization barriers or synchronization guarantees.

## -see-also

[ReadAcquire8](nf-wdm-readacquire8.md)

[ReadNoFence8](nf-wdm-readnofence8.md)

[WriteRaw8](nf-wdm-writeraw8~r1.md)

[ReadRaw](nf-wdm-readraw~r1.md)
