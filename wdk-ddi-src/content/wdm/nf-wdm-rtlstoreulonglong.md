---
UID: NF:wdm.RtlStoreUlonglong
tech.root: 
title: RtlStoreUlonglong
ms.date: 07/16/2021
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level (see Remarks)
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
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
 - RtlStoreUlonglong
f1_keywords:
 - RtlStoreUlonglong
 - wdm/RtlStoreUlonglong
dev_langs:
 - c++
---

## -description

The **RtlStoreUlonglong** macro stores a specified ULONGLONG value at a specified memory address, avoiding memory alignment faults.

## -parameters

### -param ADDRESS

[out]
A pointer to a location in which to store the specified ULONGLONG value.

### -param VALUE

[in]
The ULONGLONG value to be stored.

## -remarks

**RtlStoreUlonglong** avoids memory alignment faults. If the address specified by _Address_ is not aligned to the storage requirements of a ULONGLONG, **RtlStoreUlonglong** stores the bytes of _Value_ beginning at the memory location (PUCHAR)_Address_.

**RtlStoreUlonglong** runs at any IRQL if _Address_ points to nonpaged pool; otherwise, it must run at IRQL <= APC_LEVEL.
