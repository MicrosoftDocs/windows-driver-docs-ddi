---
UID: NS:ntddk._PHYSICAL_COUNTER_RESOURCE_LIST
title: "_PHYSICAL_COUNTER_RESOURCE_LIST"
author: windows-driver-content
description: The PHYSICAL_COUNTER_RESOURCE_LIST structure describes an array of PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structures.
old-location: kernel\physical_counter_resource_list.htm
old-project: kernel
ms.assetid: a8b22839-6a5d-48e2-a0e5-dae811d729ef
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: "*PPHYSICAL_COUNTER_RESOURCE_LIST, PHYSICAL_COUNTER_RESOURCE_LIST, PHYSICAL_COUNTER_RESOURCE_LIST structure [Kernel-Mode Driver Architecture], PPHYSICAL_COUNTER_RESOURCE_LIST, PPHYSICAL_COUNTER_RESOURCE_LIST structure pointer [Kernel-Mode Driver Architecture], _PHYSICAL_COUNTER_RESOURCE_LIST, kernel.physical_counter_resource_list, kstruct_c_17d0a58a-6ac5-4360-a481-d33f0942b521.xml, ntddk/PHYSICAL_COUNTER_RESOURCE_LIST, ntddk/PPHYSICAL_COUNTER_RESOURCE_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PHYSICAL_COUNTER_RESOURCE_LIST
product: Windows
targetos: Windows
req.typenames: PHYSICAL_COUNTER_RESOURCE_LIST, *PPHYSICAL_COUNTER_RESOURCE_LIST
---

# _PHYSICAL_COUNTER_RESOURCE_LIST structure


## -description


The <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> structure describes an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff558796">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a> structures.


## -struct-fields




### -field Count

The number of elements in the <b>Descriptors</b> array. 


### -field Descriptors

The first element in an array of <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structures. If the array contains more than one element, the remaining elements immediately follow the first element. 


## -remarks



This structure describes a set of counter resources. Most processors have performance monitor units (PMUs) that contain a number of hardware counters to measure various aspects of system performance. A counter resource is a single hardware counter, a block of contiguous counters, or a counter overflow interrupt in a PMU.

The buffer allocated to contain a <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> structure must be large enough to contain the structure plus any <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> array elements that follow the structure.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546577">HalAllocateHardwareCounters</a> routine's <i>ResourceList</i> parameter is a pointer to a <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> structure. In Windows 7, this parameter is unused and must be set to <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546577">HalAllocateHardwareCounters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558796">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a>
 

 

