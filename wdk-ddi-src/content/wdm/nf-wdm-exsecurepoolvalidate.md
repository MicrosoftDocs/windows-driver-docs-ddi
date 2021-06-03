---
UID: NF:wdm.ExSecurePoolValidate
tech.root: kernel
title: ExSecurePoolValidate
ms.date: 06/03/2021
targetos: Windows
description: The ExSecurePoolValidate function validates that the secure pool provided is indeed the one previously created.
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
 - ExSecurePoolValidate
f1_keywords:
 - ExSecurePoolValidate
 - wdm/ExSecurePoolValidate
dev_langs:
 - c++
---

## -description

The **ExSecurePoolValidate** function validates that the secure pool provided is indeed the one previously created. It matches the secure header content with the values provided and checks if it owns the heap.

## -parameters

### -param SecurePoolHandle

[in]
Supplies the handle for the heap.

### -param Tag

[in]
Supplies the pool tag for this allocation.

### -param Allocation

[in]
Supplies a pointer to the allocation it wants to validate.

### -param Cookie

[in]
Supplies a cookie value used for identifying this allocation.

## -returns

A LOGICAL value indicating if validation succeeded.

## -remarks

## -see-also
