---
UID: NF:mcd.ChangerClassAllocatePool
title: ChangerClassAllocatePool function (mcd.h)
description: The ChangerClassAllocatePool function allocates pool memory.
old-location: storage\changerclassallocatepool.htm
tech.root: storage
ms.assetid: d211bab9-4932-41c5-9b6f-528a75bb2ae4
ms.date: 03/29/2018
ms.keywords: ChangerClassAllocatePool, ChangerClassAllocatePool function [Storage Devices], chgrclas_e1b15ece-f3e4-446f-adc4-39301fc0346f.xml, mcd/ChangerClassAllocatePool, storage.changerclassallocatepool
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Mcd.lib
- Mcd.dll
api_name:
- ChangerClassAllocatePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerClassAllocatePool function


## -description


The <b>ChangerClassAllocatePool</b> function allocates pool memory. 


## -parameters




### -param PoolType [in]

Indicates the type of pool memory to allocate. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a> for a list of types.


### -param NumberOfBytes [in]

Indicates number of bytes to allocate. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>
 

 

