---
UID: NF:mcd.ChangerClassAllocatePool
title: ChangerClassAllocatePool function
author: windows-driver-content
description: The ChangerClassAllocatePool function allocates pool memory.
old-location: storage\changerclassallocatepool.htm
old-project: storage
ms.assetid: d211bab9-4932-41c5-9b6f-528a75bb2ae4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ChangerClassAllocatePool, ChangerClassAllocatePool function [Storage Devices], chgrclas_e1b15ece-f3e4-446f-adc4-39301fc0346f.xml, mcd/ChangerClassAllocatePool, storage.changerclassallocatepool
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Mcd.lib
-	Mcd.dll
api_name:
-	ChangerClassAllocatePool
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerClassAllocatePool function


## -description


The <b>ChangerClassAllocatePool</b> function allocates pool memory. 


## -syntax


````
PVOID ChangerClassAllocatePool(
  _In_ POOL_TYPE PoolType,
  _In_ ULONG     NumberOfBytes
);
````


## -parameters




### -param PoolType [in]

Indicates the type of pool memory to allocate. See <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a> for a list of types.


### -param NumberOfBytes [in]

Indicates number of bytes to allocate. 


## -returns



None




## -see-also

<a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>



 

 


