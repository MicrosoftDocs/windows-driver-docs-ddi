---
UID: NF:storport.StorPortFreeHostMemoryBuffer
title: StorPortFreeHostMemoryBuffer function (storport.h)
description: The StorPortFreeHostMemoryBuffer routine frees the physically contiguous memory that was allocated to be used for a Host Memory Buffer (HMB).
old-location: storage\storportfreehostmemorybuffer.htm
tech.root: storage
ms.assetid: 686D141E-E6EA-4BB6-8556-0ECAC592E8F0
ms.date: 03/29/2018
ms.keywords: StorPortFreeHostMemoryBuffer, StorPortFreeHostMemoryBuffer routine [Storage Devices], storage.storportfreehostmemorybuffer, storport/StorPortFreeHostMemoryBuffer
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortFreeHostMemoryBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortFreeHostMemoryBuffer function


## -description


The <b>StorPortFreeHostMemoryBuffer</b> routine frees the physically contiguous memory
    that was allocated to be used for a Host Memory Buffer (HMB) 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param PhysicalAddressRanges

The array of physical address ranges that make up
        the Host Memory Buffer previously allocated by  <b>StorPortAllocateHostMemoryBuffer</b>.


### -param PhysicalAddressRangeCount [in]

 The number of entries in <b>PhysicalAddressRanges</b>. 


## -returns



<b>StorPortFreeHostMemoryBuffer</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The host memory buffer was successfully freed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The host memory buffer was not valid (likely already freed).

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/B8413B02-32A6-40AE-9DD2-C25AD2D2D45C">StorPortAllocateHostMemoryBuffer</a>
 

 

