---
UID: NC:dispmprt.DXGKCB_AGP_FREE_POOL
title: DXGKCB_AGP_FREE_POOL
author: windows-driver-content
description: The AgpFreePool function frees AGP memory that was previously allocated by AgpAllocatePool.
old-location: display\agpfreepool.htm
tech.root: display
ms.assetid: 6d4e957e-ad9c-45da-8d1d-0ef5f108c692
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: AgpFreePool, AgpFreePool callback function [Display Devices], DXGKCB_AGP_FREE_POOL, DXGKCB_AGP_FREE_POOL callback, DpFunctions_ffe16de5-aa04-4f4b-bae5-de5b25682f65.xml, display.agpfreepool, dispmprt/AgpFreePool
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
-	AgpFreePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_AGP_FREE_POOL callback function


## -description


The <b>AgpFreePool</b> function frees AGP memory that was previously allocated by <a href="https://msdn.microsoft.com/abac76e0-eb8a-450a-a797-3733a8f71990">AgpAllocatePool</a>.


## -parameters




### -param HANDLE


### -param PVOID








#### - Context [in]

A handle to a context block that is associated with an AGP interface. The display miniport driver previously received this handle in the <b>Context</b> member of the DXGK_AGP_INTERFACE structure that was filled in by <a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>.


#### - VirtualAddress [in]

The base virtual address of the AGP allocation that is to be freed. This is the virtual address that was previously returned in the <i>VirtualAddress</i> output parameter of the <a href="https://msdn.microsoft.com/abac76e0-eb8a-450a-a797-3733a8f71990">AgpAllocatePool</a> function.


## -returns



<b>AgpFreePool</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/abac76e0-eb8a-450a-a797-3733a8f71990">AgpAllocatePool</a>



<a href="https://msdn.microsoft.com/4440bc0f-01cb-4108-bfe8-9d5127777f00">AgpSetCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560949">DXGK_AGP_INTERFACE</a>



<a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>
 

 

