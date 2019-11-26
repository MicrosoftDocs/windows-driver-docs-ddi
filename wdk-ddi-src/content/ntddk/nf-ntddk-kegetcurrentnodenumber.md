---
UID: NF:ntddk.KeGetCurrentNodeNumber
title: KeGetCurrentNodeNumber function (ntddk.h)
description: The KeGetCurrentNodeNumber routine gets the NUMA node number for the logical processor that the caller is running on.
old-location: kernel\kegetcurrentnodenumber.htm
tech.root: kernel
ms.assetid: 9b8601ad-5605-46a3-9dbe-47dc8ed5906c
ms.date: 04/30/2018
ms.keywords: KeGetCurrentNodeNumber, KeGetCurrentNodeNumber routine [Kernel-Mode Driver Architecture], k105_08763d94-700c-4662-aebe-a8aa15a7ed4f.xml, kernel.kegetcurrentnodenumber, wdm/KeGetCurrentNodeNumber
ms.topic: function
f1_keywords:
 - "ntddk/KeGetCurrentNodeNumber"
req.header: ntddk.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
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
- KeGetCurrentNodeNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetCurrentNodeNumber function


## -description


The <b>KeGetCurrentNodeNumber</b> routine gets the NUMA node number for the logical processor that the caller is running on.


## -returns



<b>KeGetCurrentNodeNumber</b> returns the node number. 




## -remarks



In a non-uniform memory access (NUMA) multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

In a NUMA multiprocessor system that contains <i>n</i> nodes, the nodes are numbered from 0 to <i>n</i>-1. To get the highest node number (<i>n</i>-1) in the system, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhighestnodenumber">KeQueryHighestNodeNumber</a> routine. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhighestnodenumber">KeQueryHighestNodeNumber</a>
 

 

