---
UID: NF:ndis.NdisSystemProcessorCount
title: NdisSystemProcessorCount function (ndis.h)
description: The NdisSystemProcessorCount function determines whether the caller is running on a uniprocessor or multiprocessor computer.
old-location: netvista\ndissystemprocessorcount.htm
tech.root: netvista
ms.assetid: 17c7b02d-3d32-4056-9baa-2fef74765da3
ms.date: 05/02/2018
keywords: ["NdisSystemProcessorCount function"]
ms.keywords: NdisSystemProcessorCount, NdisSystemProcessorCount function [Network Drivers Starting with Windows Vista], ndis/NdisSystemProcessorCount, ndis_sysinfo_ref_2bec0b11-bc24-4c8d-9e78-ff94c7f1645f.xml, netvista.ndissystemprocessorcount
f1_keywords:
 - "ndis/NdisSystemProcessorCount"
 - "NdisSystemProcessorCount"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NdisGroupMaxProcessorCount.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisSystemProcessorCount
targetos: Windows
req.typenames: 
---

# NdisSystemProcessorCount function


## -description


The 
  <b>NdisSystemProcessorCount</b> function determines whether the caller is running on a uniprocessor or
  multiprocessor computer.


## -returns



<b>NdisSystemProcessorCount</b> returns the number of processors in the computer.




## -remarks



An NDIS driver can call the 
    <b>NdisSystemProcessorCount</b> function to retrieve the maximum number of processors in the local
    computer. To retrieve the number of currently active processors, the driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemactiveprocessorcount">
    NdisSystemActiveProcessorCount</a> function.

<b>NdisSystemProcessorCount</b> is similar to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerymaximumprocessorcount">
    KeQueryMaximumProcessorCount</a> function.

The value that 
    <b>NdisSystemProcessorCount</b> returns does not change at runtime.

If your code uses an array of buffers, one buffer for each processor, you must decide whether to have
    a statically sized array based on 
    <b>NdisSystemProcessorCount</b> or a dynamically sized array based on 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemactiveprocessorcount">NdisSystemActiveProcessorCount</a>.

To optimize your code based on the number of processors, you must use a resizable structure. In this
    case, use 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemactiveprocessorcount">NdisSystemActiveProcessorCount</a>.

If you are not optimizing and if the data structures that result from using the maximum processor
    count are relatively small, a resizable structure is not necessary. In this case, use 
    <b>NdisSystemProcessorCount</b> to determine the size for a static array.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerymaximumprocessorcount">KeQueryMaximumProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgroupmaxprocessorcount">NdisGroupMaxProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemactiveprocessorcount">
   NdisSystemActiveProcessorCount</a>
 

 

