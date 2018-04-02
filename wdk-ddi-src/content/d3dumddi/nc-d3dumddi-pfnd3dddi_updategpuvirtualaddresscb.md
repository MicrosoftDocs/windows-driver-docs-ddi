---
UID: NC:d3dumddi.PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB
title: PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnUpdateGpuVirtualAddressCb is a special operation used in the context of tile resources.
old-location: display\pfnupdategpuvirtualaddresscb.htm
old-project: display
ms.assetid: 99D075A0-4483-47D1-BA24-80C45BFF407A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB, d3dumddi/pfnUpdateGpuVirtualAddressCb, display.pfnupdategpuvirtualaddresscb, pfnUpdateGpuVirtualAddressCb, pfnUpdateGpuVirtualAddressCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnUpdateGpuVirtualAddressCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB callback


## -description


<b>pfnUpdateGpuVirtualAddressCb</b> is a special operation used in the context of tile resources. It allows the user mode driver to specify a number of mapping operations to be applied to the process' virtual address space in a single batch of page table updates. 


The range of graphics processing unit (GPU) virtual addresses in all operations (except for the source address of copy operations) must belong to a single virtual address range that was obtained by calling <a href="https://msdn.microsoft.com/CEDE03E1-4B0D-4839-B7D6-0826CC103C5E">pfnReserveGpuVirtualAddressCb</a>.   Similarly, the virtual address ranges of all sources in copy operations must belong to a single virtual address range, which was obtained by calling <i>pfnReserveGpuVirtualAddressCb</i>.

The page table updates are executed on a paging context, dedicated to the rendering context specified, and executed on the GPU only after the associated rendering context signaled <b>FenceValue</b> for the specified monitored fence object. When the page table updates are finished, the paging context signals the monitored fence object to <b>FenceValue</b>+1, allowing the rendering context to do tight interlocking with the page table updates.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906767">D3DDDICB_UPDATEGPUVIRTUALADDRESS</a> structure that describes the operation to perform.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The virtual address ranges in the update operations are allowed to intersect. The operations will be applied in the order they are submitted.

In a single <b>pfnUpdateVirtualAddressCb</b> call:

<ul>
<li>All virtual address ranges in mapping operations and the destination range in copy operations must belong to the same reserved (zero) range.</li>
<li>The source virtual address range in copy operations is allowed to be from a different reserved (zero) range.</li>
<li>The source virtual address range in all copy operations must belong to the same reserved (zero) range.</li>
</ul>
The user mode driver can submit many <b>pfnUpdateGpuVirtualAddressCb</b> calls and operations will be queued behind the rendering fence. When the number of queued update operations exceeds 128, the calling thread will be blocked until the pervious operations are processed by the video memory manager.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906767">D3DDDICB_UPDATEGPUVIRTUALADDRESS</a>



<a href="https://msdn.microsoft.com/CEDE03E1-4B0D-4839-B7D6-0826CC103C5E">pfnReserveGpuVirtualAddressCb</a>
 

 

