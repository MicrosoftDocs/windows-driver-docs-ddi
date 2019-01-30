---
UID: NF:ntddk.KeQueryHighestNodeNumber
title: KeQueryHighestNodeNumber function (ntddk.h)
description: The KeQueryHighestNodeNumber routine returns the highest node number in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.
old-location: kernel\kequeryhighestnodenumber.htm
tech.root: kernel
ms.assetid: e92387db-0c35-40c8-8342-4b1bf498aa1a
ms.date: 04/30/2018
ms.keywords: KeQueryHighestNodeNumber, KeQueryHighestNodeNumber routine [Kernel-Mode Driver Architecture], k105_3d91d159-3bbb-445b-874b-a6d1a8b078df.xml, kernel.kequeryhighestnodenumber, wdm/KeQueryHighestNodeNumber
ms.topic: function
req.header: ntddk.h
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryHighestNodeNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryHighestNodeNumber function


## -description


The <b>KeQueryHighestNodeNumber</b> routine returns the highest node number in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. 


## -parameters






## -returns



<b>KeQueryHighestNodeNumber</b> returns the highest node number.




## -remarks



In a non-uniform memory access (NUMA) multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

If a NUMA multiprocessor system contains <i>n</i> nodes, the nodes are numbered from 0 to <i>n</i>-1, and <b>KeQueryHighestNodeNumber</b> returns <i>n</i>-1. If a system contains one node, <b>KeQueryHighestNodeNumber</b> returns zero.

If a system does not have a NUMA architecture, <b>KeQueryHighestNodeNumber</b> returns zero. An example of non-NUMA architecture is a symmetric multiprocessor system (SMP).

When Windows initializes a NUMA multiprocessor system, it assigns logical processors to nodes and counts the number of resulting nodes. Windows defines the capacity of a node as the number of processors that are present when the system starts in addition to any other logical processors that can be added to the node while the system is running. If, during initialization, Windows encounters a NUMA hardware node that contains more logical processors than will fit into a group, Windows splits the node into smaller, logical nodes. Each of these nodes does not exceed the maximum group size. The value that is returned by <b>KeQueryHighestNodeNumber</b> indicates the number of logical nodes in the system.

After the system has been initialized, the node count remains fixed while the system continues to run. This count might include memory-only nodes, which are nodes that contain memory but no active logical processors.



