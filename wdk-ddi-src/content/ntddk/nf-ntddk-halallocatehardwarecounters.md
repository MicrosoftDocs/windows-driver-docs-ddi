---
UID: NF:ntddk.HalAllocateHardwareCounters
title: HalAllocateHardwareCounters function (ntddk.h)
description: The HalAllocateHardwareCounters routine allocates a set of hardware performance counters.
old-location: kernel\halallocatehardwarecounters.htm
tech.root: kernel
ms.assetid: 8a689889-b445-4fda-ae11-090d0d5870b8
ms.date: 04/30/2018
keywords: ["HalAllocateHardwareCounters function"]
ms.keywords: HalAllocateHardwareCounters, HalAllocateHardwareCounters routine [Kernel-Mode Driver Architecture], k103_06a6696a-0b51-414e-96ea-6c7d3b70acb5.xml, kernel.halallocatehardwarecounters, ntddk/HalAllocateHardwareCounters
f1_keywords:
 - "ntddk/HalAllocateHardwareCounters"
 - "HalAllocateHardwareCounters"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Hal.dll
api_name:
- HalAllocateHardwareCounters
product:
- Windows
targetos: Windows
req.typenames:
ms.custom: 19H1
---

# HalAllocateHardwareCounters function


## -description


The [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) routine allocates a set of hardware performance counter resources.


## -parameters


### -param GroupAffinty

<p>A pointer to a set of <b>GROUP_AFFINITY</b> structures indicating which processors' counter resources the consumer requests. If this parameter is <b>NULL</b>, then the request indicates an allocation across all processors in the system.</p>


### -param GroupCount [in]

Supplies the number of <b>GROUP_AFFINITY</b> structures provided by the GroupAffinty parameter, or zero if GroupAffinity is <b>NULL</b>.


### -param ResourceList [in]

A pointer to a <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> containing the resources required by the consumer. If this parameter is <b>NULL</b>, then the consumer is requesting exclusive ownership of the performance monitoring unit.


### -param CounterSetHandle [out]

A pointer to a location into which the routine writes a handle to the allocated counter resources. To release these resources later, the caller must pass this handle to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-halfreehardwarecounters">HalFreeHardwareCounters</a> routine. If the requested counter resources are unavailable, [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) sets *<i>CounterSetHandle</i> = <b>NULL</b> and returns STATUS_INSUFFICIENT_RESOURCES.


## -returns



[**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) returns STATUS_SUCCESS if the call was successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The requested counter resources are currently unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid parameter value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The caller supplied resources in the resource list that are currently not supported.

</td>
</tr>
</table>
 




## -remarks



Most processors have performance monitor units (PMUs) that contain a number of hardware counters. Software tools use these counters to monitor various aspects of system performance. Typically, such a tool consists of a custom kernel-mode driver to program the counters and a user-mode application that communicates with the driver.

If more than one such tool is installed on a computer, the associated drivers must avoid trying to use the same hardware counters simultaneously. To avoid such resource conflicts, all drivers that use counter resources should use the [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) and <b>HalFreeHardwareCounters</b> routines to coordinate their sharing of these resources.

A counter resource is a single hardware counter, a block of contiguous counters, a counter overflow interrupt, or an event buffer configuration in a PMU.

Before configuring the counters, a driver can call the [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) routine to acquire exclusive access to a set of counter resources. After the driver no longer needs these resources, it must free the resources by calling the <b>HalFreeHardwareCounters</b> routine.

In versions of Windows before Windows 10 version 1903, a successful call to [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) grants the caller exclusive access to all counter resources in the performance monitor unit of a single-processor system. In a multiprocessor system, a successful call grants the caller exclusive access to all counter resources in all processors in the system. GroupAffinity and ResourceList must be <b>NULL</b> and GroupCount must be zero.

Starting in Windows 10 version 1903, counter resources can be allocated based on the resource list and group affinities provided.

Virtualization software typically does not virtualize hardware performance counters. Thus, these counters might not be available in a virtual machine, regardless of whether [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) returns a status code of STATUS_SUCCESS. For example, hardware performance counters are not available in a Hyper-V virtual machine, but [**HalAllocateHardwareCounters**](nf-ntddk-halallocatehardwarecounters.md) might still return STATUS_SUCCESS.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-halfreehardwarecounters">HalFreeHardwareCounters</a>



[**PHYSICAL_COUNTER_RESOURCE_LIST**](ns-ntddk-_physical_counter_resource_list.md)
 

 

