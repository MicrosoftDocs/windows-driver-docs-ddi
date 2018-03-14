---
UID: NF:ndis.NdisGroupActiveProcessorMask
title: NdisGroupActiveProcessorMask function
author: windows-driver-content
description: The NdisGroupActiveProcessorMask function returns the currently active processor mask for the specified group.
old-location: netvista\ndisgroupactiveprocessormask.htm
old-project: netvista
ms.assetid: 92a50a96-8bfb-4d5d-8f24-dd29794e55b1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisGroupActiveProcessorMask, NdisGroupActiveProcessorMask function [Network Drivers Starting with Windows Vista], ndis/NdisGroupActiveProcessorMask, ndis_processor_group_ref_36161079-d4a1-44ad-b7c8-1bc565efda8e.xml, netvista.ndisgroupactiveprocessormask
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
-	NdisGroupActiveProcessorMask
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGroupActiveProcessorMask function


## -description


The 
  <b>NdisGroupActiveProcessorMask</b> function returns the currently active processor mask for the specified
  group.


## -syntax


````
KAFFINITY NdisGroupActiveProcessorMask(
   USHORT Group
);
````


## -parameters




### -param Group

A USHORT value that identifies a processor group in the local computer system.


## -returns



<b>NdisGroupActiveProcessorMask</b> returns the currently active processor mask for the specified group
     as a 
     <b>KAFFINITY</b> bitmap. In an environment that allows for hot-add functionality, this bitmap can change
     during runtime.




## -remarks



An NDIS driver might call the 
    <b>NdisGroupActiveProcessorMask</b> function during initialization before it allocates resources.

The 
    <b>KAFFINITY</b> value that 
    <b>NdisGroupActiveProcessorMask</b> returns can change at runtime on SKUs that support hot-add
    functionality for CPUs.

<div class="alert"><b>Note</b>  NDIS drivers should not use the 
    <a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a> function
    to retrieve the number of currently active processors. Also, NDIS 6.20 and later drivers should not use
    the 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
    NdisSystemActiveProcessorCount</a> function because it only returns the processor count and provides
    the affinity mask as an out parameter, for processor group 0.</div>
<div> </div>
To obtain an active processor count, call the 
    <a href="..\ndis\nf-ndis-ndisgroupactiveprocessorcount.md">
    NdisGroupActiveProcessorCount</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a>



<a href="..\ndis\nf-ndis-ndisgroupactiveprocessorcount.md">
   NdisGroupActiveProcessorCount</a>



<a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
   NdisSystemActiveProcessorCount</a>



 

 


