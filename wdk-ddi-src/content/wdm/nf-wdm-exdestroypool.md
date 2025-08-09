---
UID: NF:wdm.ExDestroyPool
tech.root: kernel
title: ExDestroyPool
ms.date: 08/08/2025
targetos: Windows
description: Destroys a previously created pool instance.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: PASSIVE_LEVEL
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
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ExDestroyPool
f1_keywords:
 - ExDestroyPool
 - wdm/ExDestroyPool
dev_langs:
 - c++
ai-usage: ai-assisted
---

## -description

**ExDestroyPool** destroys a pool instance.

## -parameters

### -param PoolHandle

[in] Handle to the pool instance to be destroyed. Must be a valid handle returned by [**ExCreatePool**](nf-wdm-excreatepool.md).

## -returns

None.

## -remarks

After this call, the pool handle is no longer valid and must not be used in subsequent operations.

All allocations associated with the pool must have been released before the pool is destroyed.

If the handle is invalid, a bug check may occur.

## -see-also

[**ExCreatePool**](nf-wdm-excreatepool.md)

[**ExAllocatePool2**](nf-wdm-exallocatepool2.md)

[**ExFreePool2**](nf-wdm-exfreepool2.md)
