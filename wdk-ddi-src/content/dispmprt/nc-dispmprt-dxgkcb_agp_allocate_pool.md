---
UID: NC:dispmprt.DXGKCB_AGP_ALLOCATE_POOL
title: DXGKCB_AGP_ALLOCATE_POOL
author: windows-driver-content
description: The AgpAllocatePool function reserves, commits, and maps AGP memory.
old-location: display\agpallocatepool.htm
old-project: display
ms.assetid: abac76e0-eb8a-450a-a797-3733a8f71990
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AgpAllocatePool, AgpAllocatePool callback function [Display Devices], DXGKCB_AGP_ALLOCATE_POOL, DpFunctions_2bd4981c-c9f1-4b37-a921-9eb33d1b622b.xml, display.agpallocatepool, dispmprt/AgpAllocatePool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	AgpAllocatePool
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_AGP_ALLOCATE_POOL callback


## -description


The <b>AgpAllocatePool</b> function reserves, commits, and maps AGP memory.


## -parameters




### -param HANDLE


### -param ULONG


### -param MEMORY_CACHING_TYPE


### -param PPHYSICAL_ADDRESS


### -param PVOID








#### - AllocationSize [in]

The size, in bytes, of the AGP memory to be allocated.


#### - CacheType [in]

A constant from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554430">MEMORY_CACHING_TYPE</a> enumeration that specifies whether the CPU can use caching or write combining when it accesses the allocated AGP memory.


#### - Context [in]

A handle to a context block associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>.


#### - PhysicalAddress [out]

A pointer to a PHYSICAL_ADDRESS structure that receives the base physical address of the AGP allocation. This is the base of the physical address range that the GPU will use to access the AGP memory.


#### - VirtualAddress [out]

A pointer to a variable that receives the base virtual address, in system space, of the AGP allocation. This is the base of the virtual address range that the CPU will use to access the AGP memory.


## -returns



<b>AgpAllocatePool</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



Call <b>AgpAllocatePool</b> in the display miniport driver's <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function. It is likely that <b>AgpAllocatePool</b> will fail if you call it after <b>DxgkDdiStartDevice</b> has executed.




## -see-also




<a href="https://msdn.microsoft.com/6d4e957e-ad9c-45da-8d1d-0ef5f108c692">AgpFreePool</a>



<a href="https://msdn.microsoft.com/4440bc0f-01cb-4108-bfe8-9d5127777f00">AgpSetCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560949">DXGK_AGP_INTERFACE</a>



<a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>
 

 

