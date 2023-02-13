---
UID: NF:wdm.ExAllocateCacheAwareRundownProtection
tech.root: kernel
title: ExAllocateCacheAwareRundownProtection (wdm.h)
ms.date: 02/13/2023
targetos: Windows
description: This topic describes the ExAllocateCacheAwareRundownProtection function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: <= APC_LEVEL
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
 - DllExport
api_location:
 - wdm.h
api_name:
 - ExAllocateCacheAwareRundownProtection
f1_keywords:
 - ExAllocateCacheAwareRundownProtection
 - wdm/ExAllocateCacheAwareRundownProtection
dev_langs:
 - c++
helpviewer_keywords:
 - ExAllocateCacheAwareRundownProtection
---

## -description

This topic describes the **ExAllocateCacheAwareRundownProtection** function.

## -parameters

### -param PoolType

Defines the **POOL_TYPE** parameter *PoolType*.

### -param PoolTag

Defines the **ULONG** parameter *PoolTag*.

## -returns

Returns a pointer to a **PEX_RUNDOWN_REF_CACHE_AWARE** structure.

## -remarks

## -see-also
