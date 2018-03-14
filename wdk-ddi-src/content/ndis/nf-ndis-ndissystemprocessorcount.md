---
UID: NF:ndis.NdisSystemProcessorCount
title: NdisSystemProcessorCount function
author: windows-driver-content
description: The NdisSystemProcessorCount function determines whether the caller is running on a uniprocessor or multiprocessor computer.
old-location: netvista\ndissystemprocessorcount.htm
old-project: netvista
ms.assetid: 17c7b02d-3d32-4056-9baa-2fef74765da3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisSystemProcessorCount, NdisSystemProcessorCount function [Network Drivers Starting with Windows Vista], ndis/NdisSystemProcessorCount, ndis_sysinfo_ref_2bec0b11-bc24-4c8d-9e78-ff94c7f1645f.xml, netvista.ndissystemprocessorcount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisSystemProcessorCount
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisSystemProcessorCount function


## -description


The 
  <b>NdisSystemProcessorCount</b> function determines whether the caller is running on a uniprocessor or
  multiprocessor computer.


## -syntax


````
CCHAR NdisSystemProcessorCount(void);
````


## -parameters






## -returns



<b>NdisSystemProcessorCount</b> returns the number of processors in the computer.




## -remarks



An NDIS driver can call the 
    <b>NdisSystemProcessorCount</b> function to retrieve the maximum number of processors in the local
    computer. To retrieve the number of currently active processors, the driver must call the 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
    NdisSystemActiveProcessorCount</a> function.

<b>NdisSystemProcessorCount</b> is similar to the 
    <a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">
    KeQueryMaximumProcessorCount</a> function.

The value that 
    <b>NdisSystemProcessorCount</b> returns does not change at runtime.

If your code uses an array of buffers, one buffer for each processor, you must decide whether to have
    a statically sized array based on 
    <b>NdisSystemProcessorCount</b> or a dynamically sized array based on 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">NdisSystemActiveProcessorCount</a>.

To optimize your code based on the number of processors, you must use a resizable structure. In this
    case, use 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">NdisSystemActiveProcessorCount</a>.

If you are not optimizing and if the data structures that result from using the maximum processor
    count are relatively small, a resizable structure is not necessary. In this case, use 
    <b>NdisSystemProcessorCount</b> to determine the size for a static array.




## -see-also

<a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">KeQueryMaximumProcessorCount</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\ndis\nf-ndis-ndisgroupmaxprocessorcount.md">NdisGroupMaxProcessorCount</a>



<a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
   NdisSystemActiveProcessorCount</a>



 

 


