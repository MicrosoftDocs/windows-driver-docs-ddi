---
UID: NF:wdm.KeQueryNodeActiveAffinity2
tech.root: kernel
title: KeQueryNodeActiveAffinity2
ms.date: 04/19/2021
targetos: Windows
description: This routine returns the current multi-group processor affinity of the given NUMA node.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - KeQueryNodeActiveAffinity2
f1_keywords:
 - KeQueryNodeActiveAffinity2
 - wdm/KeQueryNodeActiveAffinity2
dev_langs:
 - c++
---

## -description

This routine returns the current multi-group processor affinity of the given NUMA node.

## -parameters

### -param NodeNumber

[in]

Supplies the node number of the node to query.

### -param GroupAffinities

[out]

Supplies a pointer to an array of <a href="/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a> structures that upon success receive a group number and the affinity mask of the identified group.

### -param GroupAffinitiesCount

[in]

A value of type USHORT that specifies the number of elements in the group affinities array. If the array is too small to hold the node affinity then **STATUS_BUFFER_TOO_SMALL** is returned and the number of elements required is returned in *GroupAffinitiesRequired*.

### -param GroupAffinitiesRequired

[out]

A pointer to a value of type USHORT that receives the number of group affinities required to represent the node affinity. In the case of a memory-only NUMA node, zero is returned.

## -returns

**STATUS_SUCCESS** if the node affinity was queried successfully.

**STATUS_INVALID_PARAMETER** if an invalid node number was specified.

**STATUS_BUFFER_TOO_SMALL** if the supplied array is too small.

## -remarks

Starting in Windows Server 2022, the operating system no longer splits large NUMA nodes; instead, Windows reports the true NUMA topology of the system. When a node contains more than 64 processors, a NUMA node spans across more than a single group. In this case, the system assigns a primary group for each NUMA node. The primary group is always the one containing the most processors. To determine the number of active processors in a given NUMA node (across all groups), call [**KeQueryNodeActiveProcessorCount**](./nf-wdm-kequerynodeactiveprocessorcount.md). For more info about this change in behavior, see [NUMA Support](/windows/win32/procthread/numa-support).

> [!NOTE]
> To re-enable the legacy node splitting behavior, make the following change to the registry and reboot the system:
> `reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\NUMA" /v SplitLargeNodes /t REG_DWORD /d 1`


If your driver maps processors to NUMA nodes by calling [**KeQueryNodeActiveAffinity**](./nf-wdm-kequerynodeactiveaffinity.md), and your code runs on systems with more than 64 processors per NUMA node, use one of the following workarounds:

1. Migrate to the multi-group node affinity APIs (user-mode and kernel-mode), such as **KeQueryNodeActiveAffinity2**.
2. Call [**KeQueryLogicalProcessorRelationship**](./nf-wdm-kequerylogicalprocessorrelationship.md) with **RelationNumaNode** to directly query the NUMA node associated with a given processor number.

The following code example shows code that would be problematic on Windows Server 2022 and later, and then shows both workarounds.


```cpp
//
// Problematic implementation using KeQueryNodeActiveAffinity.
//

    USHORT CurrentNode;
    USHORT HighestNodeNumber;
    GROUP_AFFINITY NodeAffinity;
    ULONG ProcessorIndex;
    PROCESSOR_NUMBER ProcessorNumber;

    HighestNodeNumber = KeQueryHighestNodeNumber();
    for (CurrentNode = 0; CurrentNode <= HighestNodeNumber; CurrentNode += 1) {

        KeQueryNodeActiveAffinity(CurrentNode, &NodeAffinity, NULL);
        while (NodeAffinity.Mask != 0) {

            ProcessorNumber.Group = NodeAffinity.Group;
            BitScanForward(&ProcessorNumber.Number, NodeAffinity.Mask);

            ProcessorIndex = KeGetProcessorIndexFromNumber(&ProcessorNumber);

            ProcessorNodeContexts[ProcessorIndex] = NodeContexts[CurrentNode;]

            NodeAffinity.Mask &= ~((KAFFINITY)1 << ProcessorNumber.Number);
        }
    }

//
// Resolution using KeQueryNodeActiveAffinity2.
//

    USHORT CurrentIndex;
    USHORT CurrentNode;
    USHORT CurrentNodeAffinityCount;
    USHORT HighestNodeNumber;
    ULONG MaximumGroupCount;
    PGROUP_AFFINITY NodeAffinityMasks;
    ULONG ProcessorIndex;
    PROCESSOR_NUMBER ProcessorNumber;
    NTSTATUS Status;

    MaximumGroupCount = KeQueryMaximumGroupCount();
    NodeAffinityMasks = ExAllocatePool2(POOL_FLAG_PAGED,
                                        sizeof(GROUP_AFFINITY) * MaximumGroupCount,
                                        'tseT');

    if (NodeAffinityMasks == NULL) {
        return STATUS_NO_MEMORY;
    }

    HighestNodeNumber = KeQueryHighestNodeNumber();
    for (CurrentNode = 0; CurrentNode <= HighestNodeNumber; CurrentNode += 1) {

        Status = KeQueryNodeActiveAffinity2(CurrentNode,
                                            NodeAffinityMasks,
                                            MaximumGroupCount,
                                            &CurrentNodeAffinityCount);
        NT_ASSERT(NT_SUCCESS(Status));

        for (CurrentIndex = 0; CurrentIndex < CurrentNodeAffinityCount; CurrentIndex += 1) {

            CurrentAffinity = &NodeAffinityMasks[CurrentIndex];

            while (CurrentAffinity->Mask != 0) {

                ProcessorNumber.Group = CurrentAffinity.Group;
                BitScanForward(&ProcessorNumber.Number, CurrentAffinity->Mask);

                ProcessorIndex = KeGetProcessorIndexFromNumber(&ProcessorNumber);

                ProcessorNodeContexts[ProcessorIndex] = NodeContexts[CurrentNode];

                CurrentAffinity->Mask &= ~((KAFFINITY)1 << ProcessorNumber.Number);
            }
        }
    }

//
// Resolution using KeQueryLogicalProcessorRelationship.
//

    ULONG ProcessorCount;
    ULONG ProcessorIndex;
    SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX ProcessorInformation;
    ULONG ProcessorInformationSize;
    PROCESSOR_NUMBER ProcessorNumber;
    NTSTATUS Status;

    ProcessorCount = KeQueryActiveProcessorCountEx(ALL_PROCESSOR_GROUPS);

    for (ProcessorIndex = 0; ProcessorIndex < ProcessorCount; ProcessorIndex += 1) {

        Status = KeGetProcessorNumberFromIndex(ProcessorIndex, &ProcessorNumber);
        NT_ASSERT(NT_SUCCESS(Status));

        ProcessorInformationSize = sizeof(ProcessorInformation);
        Status = KeQueryLogicalProcessorRelationship(&ProcessorNumber,
                                                     RelationNumaNode,
                                                     &ProcessorInformation,
                                                     &ProcesorInformationSize);
        NT_ASSERT(NT_SUCCESS(Status));

        NodeNumber = ProcessorInformation.NumaNode.NodeNumber;

        ProcessorNodeContexts[ProcessorIndex] = NodeContexts[NodeNumber];
    }
```

## -see-also

[**KeQueryNodeActiveAffinity**](./nf-wdm-kequerynodeactiveaffinity.md)

[**KeQueryNodeActiveProcessorCount**](./nf-wdm-kequerynodeactiveprocessorcount.md)

[NUMA Support](/windows/win32/procthread/numa-support)
