---
UID: NF:wdm.KeQueryNodeMaximumProcessorCount
title: KeQueryNodeMaximumProcessorCount function (wdm.h)
description: The KeQueryNodeMaximumProcessorCount routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain.
old-location: kernel\kequerynodemaximumprocessorcount.htm
tech.root: kernel
ms.assetid: 56688002-d481-45a6-bfb0-e7761f9ae055
ms.date: 04/30/2018
keywords: ["KeQueryNodeMaximumProcessorCount function"]
ms.keywords: KeQueryNodeMaximumProcessorCount, KeQueryNodeMaximumProcessorCount routine [Kernel-Mode Driver Architecture], k105_15c5df15-b04a-41bd-9aec-2e402e2824a9.xml, kernel.kequerynodemaximumprocessorcount, wdm/KeQueryNodeMaximumProcessorCount
f1_keywords:
 - "wdm/KeQueryNodeMaximumProcessorCount"
 - "KeQueryNodeMaximumProcessorCount"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeQueryNodeMaximumProcessorCount
targetos: Windows
req.typenames: 
---

# KeQueryNodeMaximumProcessorCount function


## -description


The <b>KeQueryNodeMaximumProcessorCount</b> routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain. 


## -parameters




### -param NodeNumber 
[in]
The node number. If a NUMA multiprocessor system contains <i>n</i> nodes, valid node numbers are in the range 0 to <i>n</i>-1. To get the highest node number (<i>n</i>-1) in the system, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhighestnodenumber">KeQueryHighestNodeNumber</a> routine. 


## -returns



<b>KeQueryNodeMaximumProcessorCount</b> returns the maximum number of logical processors.




## -remarks



In a multiprocessor system with a NUMA architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

The count returned by this routine includes any logical processors that can be dynamically added to the node while the multiprocessor system is running.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhighestnodenumber">KeQueryHighestNodeNumber</a>
 

 

