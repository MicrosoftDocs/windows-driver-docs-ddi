---
UID: NF:ndis.NdisInterlockedDecrement
title: NdisInterlockedDecrement macro (ndis.h)
description: The NdisInterlockedDecrement function decrements a caller-supplied variable of type LONG as an atomic operation.
old-location: netvista\ndisinterlockeddecrement.htm
tech.root: netvista
ms.assetid: cf425cd6-88e6-479f-a5c7-364ae896145d
ms.date: 05/02/2018
keywords: ["NdisInterlockedDecrement macro"]
ms.keywords: NdisInterlockedDecrement, NdisInterlockedDecrement macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedDecrement, ndis_interlocked_ref_bbf1ad9d-0f18-4746-9fa3-b2b2c4101a41.xml, netvista.ndisinterlockeddecrement
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInterlockedDecrement (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInterlockedDecrement (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisInterlockedDecrement
 - ndis/NdisInterlockedDecrement
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisInterlockedDecrement
---

# NdisInterlockedDecrement macro


## -description

The 
  <b>NdisInterlockedDecrement</b> function decrements a caller-supplied variable of type LONG as an atomic
  operation.

## -parameters

### -param Addend 

[in]
A pointer to the variable to be decremented.

## -returns

**NdisInterlockedDecrement** returns the decremented value.

## -remarks

<b>NdisInterlockedDecrement</b> can safely be used on variables in pageable memory.

<b>NdisInterlockedDecrement</b> is atomic only with respect to other 
    <b>NdisInterlocked<i>Xxx</i></b> calls.

This macro is a wrapper around the [**InterlockedDecrement**](../wdm/nf-wdm-interlockeddecrement.md) macro.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinterlockedincrement">NdisInterlockedIncrement</a>