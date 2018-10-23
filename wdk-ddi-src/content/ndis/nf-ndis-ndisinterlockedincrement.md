---
UID: NF:ndis.NdisInterlockedIncrement
title: NdisInterlockedIncrement macro
author: windows-driver-content
description: The NdisInterlockedIncrement function increments a caller-supplied variable as an atomic operation.
old-location: netvista\ndisinterlockedincrement.htm
tech.root: netvista
ms.assetid: 246ded7a-4f75-469d-bdba-860ce3cd6b44
ms.date: 05/02/2018
ms.keywords: NdisInterlockedIncrement, NdisInterlockedIncrement macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedIncrement, ndis_interlocked_ref_1f82d382-098a-489c-8c9b-ea0bb34d352a.xml, netvista.ndisinterlockedincrement
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInterlockedIncrement (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInterlockedIncrement (NDIS   5.1)) in Windows XP.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInterlockedIncrement
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInterlockedIncrement macro


## -description


The 
  <b>NdisInterlockedIncrement</b> function increments a caller-supplied variable as an atomic
  operation.


## -parameters




### -param Addend [in]

A pointer to a variable of type LONG.


## -remarks



<b>NdisInterlockedIncrement</b> cannot be used on variables in pageable memory.

<b>NdisInterlockedIncrement</b> is atomic only with respect to other 
    <b>NdisInterlocked<i>Xxx</i></b> calls.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562751">NdisInterlockedDecrement</a>
 

 

