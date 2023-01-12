---
UID: NF:wdm.KeQueryNodeActiveAffinity
title: KeQueryNodeActiveAffinity function (wdm.h)
description: The KeQueryNodeActiveAffinity routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.
tech.root: kernel
ms.date: 01/05/2023
keywords: ["KeQueryNodeActiveAffinity function"]
ms.keywords: KeQueryNodeActiveAffinity, KeQueryNodeActiveAffinity routine [Kernel-Mode Driver Architecture], k105_05e2547a-e13e-4ade-9139-29690a72e9ed.xml, kernel.kequerynodeactiveaffinity, wdm/KeQueryNodeActiveAffinity
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KeQueryNodeActiveAffinity
 - wdm/KeQueryNodeActiveAffinity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeQueryNodeActiveAffinity
---

## -description

The **KeQueryNodeActiveAffinity** routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.

## -parameters

### -param NodeNumber [in]

The node number. If a multiprocessor system contains *n* nodes, the nodes are numbered from 0 to *n*-1. To obtain the highest node number (*n*-1) in the system, call the [KeQueryHighestNodeNumber](../ntddk/nf-ntddk-kequeryhighestnodenumber.md) routine.

### -param Affinity [out, optional]

A pointer to a caller-allocated buffer into which the routine writes a [**GROUP_AFFINITY**](../miniport/ns-miniport-_group_affinity.md) structure. This structure contains the group number of the group that contains the node that is identified by *NodeNumber*, and an affinity mask that indicates which logical processors in the node are active. You can set this parameter to **NULL** if you do not need this information.

Starting in Windows Server 2022, a node can span more than one group. This happens when a node contains more than 64 processors. In this case, the OS assigns a primary group for each NUMA node. The primary group is always the one containing the most processors. In this case, the group affinity structure returned is for the node's primary group. For more info about this change in behavior, see [NUMA Support](/windows/win32/procthread/numa-support). If your code runs on systems with more than 64 processors per NUMA node, consider instead using [**KeQueryNodeActiveAffinity2**](./nf-wdm-kequerynodeactiveaffinity2.md).

### -param Count [out, optional]

A pointer to a location into which the routine writes the number of active processors that are represented in the node affinity mask that is pointed to by *Affinity*. You can set this parameter to **NULL** if you do not need this information.

Starting in Windows Server 2022, count returned is for the node's primary group. See more info about primary groups above.

## -remarks

The caller-allocated buffer that is pointed to by the *Affinity* parameter must be large enough to contain a **GROUP_AFFINITY** structure. The **Mask** member of this structure contains an affinity mask that indicates which processors are active. If a processor is active, the corresponding bit in the mask is one. All other bits are zero.

In a NUMA multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

The number of processors in a node cannot exceed the number of bits in the affinity mask in the structure that is pointed to by *Affinity*. The affinity mask also determines the maximum number of processors in a group.

In Windows 10, version 2004 and earlier versions, if during system initialization, Windows encounters a NUMA hardware node that contains more logical processors than will fit into a group, Windows splits the node into smaller, logical nodes. Each of these nodes does not exceed the maximum group size. The *NodeNumber* parameter identifies a logical node. To obtain the maximum number of processors per group, call the [KeQueryMaximumProcessorCountEx](../ntddk/nf-ntddk-kequerymaximumprocessorcountex.md) routine.

## -see-also

[KeQueryNodeActiveAffinity2](./nf-wdm-kequerynodeactiveaffinity2.md)

[KeQueryLogicalProcessorRelationship](./nf-wdm-kequerylogicalprocessorrelationship.md)

[**GROUP_AFFINITY**](../miniport/ns-miniport-_group_affinity.md)

[KeQueryHighestNodeNumber](../ntddk/nf-ntddk-kequeryhighestnodenumber.md)

[KeQueryHighestNodeNumber](../ntddk/nf-ntddk-kequeryhighestnodenumber.md)

[KeQueryMaximumProcessorCountEx](../ntddk/nf-ntddk-kequerymaximumprocessorcountex.md)
