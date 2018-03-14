---
UID: NF:ntddk.KeQueryNodeActiveAffinity
title: KeQueryNodeActiveAffinity function
author: windows-driver-content
description: The KeQueryNodeActiveAffinity routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.
old-location: kernel\kequerynodeactiveaffinity.htm
old-project: kernel
ms.assetid: 49d4c9c7-217f-41b7-b870-886dd78e04a9
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeQueryNodeActiveAffinity, KeQueryNodeActiveAffinity routine [Kernel-Mode Driver Architecture], k105_05e2547a-e13e-4ade-9139-29690a72e9ed.xml, kernel.kequerynodeactiveaffinity, wdm/KeQueryNodeActiveAffinity
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	KeQueryNodeActiveAffinity
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# KeQueryNodeActiveAffinity function


## -description


The <b>KeQueryNodeActiveAffinity</b> routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.


## -syntax


````
VOID KeQueryNodeActiveAffinity(
  _In_      USHORT          NodeNumber,
  _Out_opt_ PGROUP_AFFINITY Affinity,
  _Out_opt_ PUSHORT         Count
);
````


## -parameters




### -param NodeNumber [in]

The node number. If a multiprocessor system contains <i>n</i> nodes, the nodes are numbered from 0 to <i>n</i>-1. To obtain the highest node number (<i>n</i>-1) in the system, call the <a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a> routine. 


### -param Affinity [out, optional]

A pointer to a caller-allocated buffer into which the routine writes a <a href="..\minitape\ns-minitape-_group_affinity.md">GROUP_AFFINITY</a> structure. This structure contains the group number of the group that contains the node that is identified by <i>NodeNumber</i>, and an affinity mask that indicates which logical processors in the node are active. You can set this parameter to <b>NULL</b> if you do not need this information. 


### -param Count [out, optional]

A pointer to a location into which the routine writes the number of active processors that are represented in the node affinity mask that is pointed to by <i>Affinity</i>. You can set this parameter to <b>NULL</b> if you do not need this information. 


## -returns



None




## -remarks



The caller-allocated buffer that is pointed to by the <i>Affinity</i> parameter must be large enough to contain a <b>GROUP_AFFINITY</b> structure. The <b>Mask</b> member of this structure contains an affinity mask that indicates which processors are active. If a processor is active, the corresponding bit in the mask is one. All other bits are zero.

In a NUMA multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

The number of processors in a node cannot exceed the number of bits in the affinity mask in the structure that is pointed to by <i>Affinity</i>. The affinity mask also determines the maximum number of processors in a group.

If, during system initialization, Windows encounters a NUMA hardware node that contains more logical processors than will fit into a group, Windows splits the node into smaller, logical nodes. Each of these nodes does not exceed the maximum group size. The <i>NodeNumber</i> parameter identifies a logical node. To obtain the maximum number of processors per group, call the <a href="..\wdm\nf-wdm-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a> routine.




## -see-also

<a href="..\minitape\ns-minitape-_group_affinity.md">GROUP_AFFINITY</a>



<a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a>



<a href="..\wdm\nf-wdm-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a>



 

 


