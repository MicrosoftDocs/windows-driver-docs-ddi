---
UID: NF:wdm.ReadRaw16~r1
tech.root: kernel
title: ReadRaw16
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw read operation on a volatile SHORT value without any memory ordering or atomicity semantics.
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
 - ReadRaw16
f1_keywords:
 - ReadRaw16
 - wdm/ReadRaw16
dev_langs:
 - c++
helpviewer_keywords:
 - ReadRaw16
---

## -description

**ReadRaw16** performs a raw read operation on a volatile SHORT value without any memory ordering or atomicity semantics.

## -parameters

### -param Source

[in] A pointer to the volatile SHORT variable to read from.

## -returns

Returns the SHORT value read from the specified memory location.

## -remarks

The **ReadRaw16** function performs a raw memory read operation on a 16-bit value without compiler optimization barriers or synchronization guarantees. It's useful on strongly-ordered architectures where precise control over memory access is required.

## -see-also

[ReadAcquire16](nf-wdm-readacquire16.md)

[ReadNoFence16](nf-wdm-readnofence16.md)

[WriteRaw16](nf-wdm-writeraw16~r1.md)

[ReadRaw](nf-wdm-readraw~r1.md)
