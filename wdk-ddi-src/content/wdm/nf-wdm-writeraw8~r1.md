---
UID: NF:wdm.WriteRaw8~r1
tech.root: kernel
title: WriteRaw8
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw write operation to a volatile CHAR value without any memory ordering or atomicity semantics.
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
 - WriteRaw8
f1_keywords:
 - WriteRaw8
 - wdm/WriteRaw8
dev_langs:
 - c++
helpviewer_keywords:
 - WriteRaw8
---

## -description

**WriteRaw8** performs a raw write operation to a volatile CHAR value without any memory ordering or atomicity semantics.

## -parameters

### -param Destination

[out] A pointer to the volatile CHAR variable to write to.

### -param Value

[in] The CHAR value to write to the destination.

## -remarks

The **WriteRaw8** function performs a raw memory write operation on an 8-bit value without compiler optimization barriers or synchronization guarantees.

## -see-also

[ReadRaw8](nf-wdm-readraw8-r1.md)

[WriteRaw](nf-wdm-writeraw-r1.md)
