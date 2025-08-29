---
UID: NF:wdm.WriteRaw16~r1
tech.root: kernel
title: WriteRaw16
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw write operation to a volatile SHORT value without any memory ordering or atomicity semantics.
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
 - WriteRaw16
f1_keywords:
 - WriteRaw16
 - wdm/WriteRaw16
dev_langs:
 - c++
helpviewer_keywords:
 - WriteRaw16
---

## -description

**WriteRaw16** performs a raw write operation to a volatile SHORT value without any memory ordering or atomicity semantics.

## -parameters

### -param Destination

[out] A pointer to the volatile SHORT variable to write to.

### -param Value

[in] The SHORT value to write to the destination.

## -remarks

The **WriteRaw16** function performs a raw memory write operation on a 16-bit value without compiler optimization barriers or synchronization guarantees.

## -see-also

[ReadRaw16](nf-wdm-readraw16-r1.md)

[WriteRaw](nf-wdm-writeraw-r1.md)
