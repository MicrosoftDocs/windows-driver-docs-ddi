---
UID: NF:ndis.NdisCurrentGroupAndProcessor
title: NdisCurrentGroupAndProcessor function
author: windows-driver-content
description: The NdisCurrentGroupAndProcessor function returns the group-relative processor number and group number of the current processor.
old-location: netvista\ndiscurrentgroupandprocessor.htm
old-project: netvista
ms.assetid: 056f7f4b-152b-426a-b59e-0f6663b386a8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisCurrentGroupAndProcessor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCurrentGroupAndProcessor
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: >= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCurrentGroupAndProcessor function



## -description
The
  <b>NdisCurrentGroupAndProcessor</b> function returns the group-relative processor number and group number of
  the current processor.



## -syntax

````
PROCESSOR_NUMBER NdisCurrentGroupAndProcessor(void);
````


## -parameters


## -returns
<b>NdisCurrentGroupAndProcessor</b> returns a PROCESSOR_NUMBER value that contains the group-relative
     processor number and group number of the current processor.

<b>NdisCurrentGroupAndProcessor</b> returns a PROCESSOR_NUMBER value that contains the group-relative
     processor number and group number of the current processor.

<b>NdisCurrentGroupAndProcessor</b> returns a PROCESSOR_NUMBER value that contains the group-relative
     processor number and group number of the current processor.


## -remarks
NDIS drivers call the 
    <b>NdisCurrentGroupAndProcessor</b> function to obtain the group-relative processor number and group
    number of the current processor.

The PROCESSOR_NUMBER structure contains a 
    <b>Group</b> member of type USHORT and a 
    <b>Number</b> member of type UCHAR for group and processor numbers, respectively. The group and processor
    numbers are zero-based values.</p>