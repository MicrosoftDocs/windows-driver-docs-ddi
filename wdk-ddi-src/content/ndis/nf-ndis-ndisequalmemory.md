---
UID: NF:ndis.NdisEqualMemory
title: NdisEqualMemory macro
author: windows-driver-content
description: The NdisEqualMemory function compares a specified number of characters in one block of memory with the same number of characters in a second block of memory.
old-location: netvista\ndisequalmemory.htm
old-project: netvista
ms.assetid: 5417b821-b51d-4789-8380-f93d113f42d3
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisEqualMemory, NdisEqualMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisEqualMemory, ndis_memory_ref_67be2fe2-f491-4b7d-9524-a4e324630f74.xml, netvista.ndisequalmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualMemory instead.
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
req.lib: 
req.dll: 
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisEqualMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisEqualMemory macro


## -description


The 
  <b>NdisEqualMemory</b> function compares a specified number of characters in one block of memory with the
  same number of characters in a second block of memory.


## -parameters




### -param Source1

A pointer to the first block of memory to be compared.


### -param Source2

A pointer to the second block of memory to be compared.


### -param Length

The number of bytes to be compared.


## -remarks



<b>NdisEqualMemory</b> compares two blocks of memory and uses the value that is specified in the 
    <i>Length</i> parameter for both blocks. The data type of anything in the compared memory blocks is
    irrelevant.

Callers of 
    <b>NdisEqualMemory</b> can be running at IRQL &lt;= DISPATCH_LEVEL if both memory blocks are resident. If
    either block is pageable, callers must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561870">RtlFillMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563610">RtlZeroMemory</a>
 

 

