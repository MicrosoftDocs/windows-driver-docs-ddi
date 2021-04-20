---
UID: NF:wdm.KeQueryNodeActiveProcessorCount
tech.root: kernel
title: KeQueryNodeActiveProcessorCount
ms.date: 04/19/2021
targetos: Windows
description: This routine returns the number of active processors in the given NUMA node across all groups.
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
 - 
api_location:
 - wdm.h
api_name:
 - KeQueryNodeActiveProcessorCount
f1_keywords:
 - KeQueryNodeActiveProcessorCount
 - wdm/KeQueryNodeActiveProcessorCount
dev_langs:
 - c++
---

## -description

This routine returns the number of active processors in the given NUMA node across all groups.

## -parameters

### -param NodeNumber

[in]

A value of type USHORT that specifies the node number of the node to query.

## -returns

Returns the number of active processors in the specified NUMA node or zero if an invalid node number was specified.

## -remarks

## -see-also

[**KeQueryNodeActiveAffinity2**](./nf-wdm-kequerynodeactiveaffinity2.md)

[NUMA Support](/windows/win32/procthread/numa-support)
