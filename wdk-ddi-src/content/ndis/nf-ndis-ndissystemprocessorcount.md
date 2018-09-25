---
UID: NF:ndis.NdisSystemProcessorCount
title: NdisSystemProcessorCount function
author: windows-driver-content
description: The NdisSystemProcessorCount function determines whether the caller is running on a uniprocessor or multiprocessor computer.
old-location: netvista\ndissystemprocessorcount.htm
tech.root: netvista
ms.assetid: 17c7b02d-3d32-4056-9baa-2fef74765da3
ms.author: windowsdriverdev
ms.date: 5/2/2018
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSystemProcessorCount function


## -description


The 
  <b>NdisSystemProcessorCount</b> function determines whether the caller is running on a uniprocessor or
  multiprocessor computer.


## -parameters






## -returns



<b>NdisSystemProcessorCount</b> returns the number of processors in the computer.




## -remarks



An NDIS driver can call the 
    <b>NdisSystemProcessorCount</b> function to retrieve the maximum number of processors in the local
    computer. To retrieve the number of currently active processors, the driver must call the 
    <a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
    NdisSystemActiveProcessorCount</a> function.

<b>NdisSystemProcessorCount</b> is similar to the 
    <a href="https://msdn.microsoft.com/bab2c478-4e46-40d9-a4b6-6f322b18ab0a">
    KeQueryMaximumProcessorCount</a> function.

The value that 
    <b>NdisSystemProcessorCount</b> returns does not change at runtime.

If your code uses an array of buffers, one buffer for each processor, you must decide whether to have
    a statically sized array based on 
    <b>NdisSystemProcessorCount</b> or a dynamically sized array based on 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564577">NdisSystemActiveProcessorCount</a>.

To optimize your code based on the number of processors, you must use a resizable structure. In this
    case, use 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564577">NdisSystemActiveProcessorCount</a>.

If you are not optimizing and if the data structures that result from using the maximum processor
    count are relatively small, a resizable structure is not necessary. In this case, use 
    <b>NdisSystemProcessorCount</b> to determine the size for a static array.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553042">KeQueryMaximumProcessorCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562689">NdisGroupMaxProcessorCount</a>



<a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
   NdisSystemActiveProcessorCount</a>
 

 

