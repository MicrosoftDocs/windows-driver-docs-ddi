---
UID: NF:wdm.ExSecurePoolUpdate
tech.root: kernel
title: ExSecurePoolUpdate
ms.date: 06/03/2021
targetos: Windows
description: The ExSecurePoolUpdate function updates the contents of the secure pool allocation.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - ExSecurePoolUpdate
f1_keywords:
 - ExSecurePoolUpdate
 - wdm/ExSecurePoolUpdate
dev_langs:
 - c++
---

## -description

The **ExSecurePoolUpdate** function updates the contents of the secure pool allocation.

## -parameters

### -param SecurePoolHandle [in]


Supplies the handle for the heap.

### -param Tag [in]


Supplies the tag for this allocation.

### -param Allocation [in]


Supplies a pointer to the allocation it wants to update.

### -param Cookie [in]


Supplies a cookie value used for identifying this allocation.

### -param Offset [in]


Supplies the offset into the buffer to be modified.

### -param Size [in]


Supplies size of the allocation. Offset + size must be within the original allocation.

### -param Buffer [in]


Supplies new contents of the secure pool block.

## -returns

Returns an NTSTATUS code.

## -remarks

## -see-also
