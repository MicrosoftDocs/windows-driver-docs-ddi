---
UID: NF:ndis.NdisGroupMaxProcessorCount
title: NdisGroupMaxProcessorCount function (ndis.h)
description: The NdisGroupMaxProcessorCount function determines the maximum number of processors in a specified processor group.
old-location: netvista\ndisgroupmaxprocessorcount.htm
tech.root: netvista
ms.assetid: 545a5014-aa07-49ee-92b7-2ae95f4ce785
ms.date: 05/02/2018
keywords: ["NdisGroupMaxProcessorCount function"]
ms.keywords: NdisGroupMaxProcessorCount, NdisGroupMaxProcessorCount function [Network Drivers Starting with Windows Vista], ndis/NdisGroupMaxProcessorCount, ndis_processor_group_ref_6bee6183-d82f-4512-a05d-134a95e898ae.xml, netvista.ndisgroupmaxprocessorcount
f1_keywords:
 - "ndis/NdisGroupMaxProcessorCount"
 - "NdisGroupMaxProcessorCount"
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
- NdisGroupMaxProcessorCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGroupMaxProcessorCount function


## -description


The 
  <b>NdisGroupMaxProcessorCount</b> function determines the maximum number of processors in a specified
  processor group.


## -parameters




### -param Group

A USHORT value that identifies a processor group in the local computer system.


## -returns



<b>NdisGroupMaxProcessorCount</b> returns a ULONG value for the maximum number of processors that are
      included in the group that is specified in the 
      <i>Group</i> parameter. The number of processors is a zero-based value.

If the 
      <i>Group</i> parameter is ALL_PROCESSOR_GROUPS, 
      <b>NdisGroupMaxProcessorCount</b> returns the maximum number of processors in the local computer.




## -remarks



An NDIS driver might call the 
    <b>NdisGroupMaxProcessorCount</b> function during initialization before it allocates resources.

<div class="alert"><b>Note</b>  NDIS 6.20 and later drivers should not use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemprocessorcount">NdisSystemProcessorCount</a> function
    because it only returns the processor count for processor group 0.</div>
<div> </div>
The processor count can change at runtime on SKUs that support hot-add functionality for CPUs. To
    obtain an active processor count, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgroupactiveprocessorcount">
    NdisGroupActiveProcessorCount</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgroupactiveprocessorcount">
   NdisGroupActiveProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemprocessorcount">NdisSystemProcessorCount</a>
 

 

