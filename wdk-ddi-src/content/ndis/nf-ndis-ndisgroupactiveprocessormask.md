---
UID: NF:ndis.NdisGroupActiveProcessorMask
title: NdisGroupActiveProcessorMask function (ndis.h)
description: The NdisGroupActiveProcessorMask function returns the currently active processor mask for the specified group.
old-location: netvista\ndisgroupactiveprocessormask.htm
tech.root: netvista
ms.assetid: 92a50a96-8bfb-4d5d-8f24-dd29794e55b1
ms.date: 05/02/2018
ms.keywords: NdisGroupActiveProcessorMask, NdisGroupActiveProcessorMask function [Network Drivers Starting with Windows Vista], ndis/NdisGroupActiveProcessorMask, ndis_processor_group_ref_36161079-d4a1-44ad-b7c8-1bc565efda8e.xml, netvista.ndisgroupactiveprocessormask
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisGroupActiveProcessorMask
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGroupActiveProcessorMask function


## -description


The 
  <b>NdisGroupActiveProcessorMask</b> function returns the currently active processor mask for the specified
  group.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564579">NdisSystemProcessorCount</a> function
    to retrieve the number of currently active processors. Also, NDIS 6.20 and later drivers should not use
    the 
    <a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
    NdisSystemActiveProcessorCount</a> function because it only returns the processor count and provides
    the affinity mask as an out parameter, for processor group 0.</div>
<div> </div>
To obtain an active processor count, call the 
    <a href="https://msdn.microsoft.com/d6631aa7-e3ba-4768-a55a-6a66d1ee84c6">
    NdisGroupActiveProcessorCount</a> function.




## -see-also




<a href="https://msdn.microsoft.com/d6631aa7-e3ba-4768-a55a-6a66d1ee84c6">
   NdisGroupActiveProcessorCount</a>



<a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
   NdisSystemActiveProcessorCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564579">NdisSystemProcessorCount</a>
 

 

