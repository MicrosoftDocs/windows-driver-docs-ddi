---
UID: NC:d3dkmddi.DXGKCB_CREATECONTEXTALLOCATION
title: DXGKCB_CREATECONTEXTALLOCATION
author: windows-driver-content
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to allocate a GPU context or device-specific context.
old-location: display\dxgkcbcreatecontextallocation.htm
ms.assetid: b6b142a4-20eb-4368-bd7f-8a25f4fe48ca
ms.date: 5/10/2018
ms.keywords: DXGKCB_CREATECONTEXTALLOCATION, DXGKCB_CREATECONTEXTALLOCATION callback, DxgkCbCreateContextAllocation, DxgkCbCreateContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbCreateContextAllocation, display.dxgkcbcreatecontextallocation
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmddi.h
api_name:
-	DxgkCbCreateContextAllocation
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_CREATECONTEXTALLOCATION callback function


## -description


Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to allocate a GPU context or device-specific context.


## -parameters


### -param 

*ContextAllocation* 

[in, out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451242">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure that specifies the attributes of the context to be allocated.


## -returns



<i>DxgkCbCreateContextAllocation</i> returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



Starting with WDDM 1.2, display miniport drivers can allocate a GPU-specific context (<i>GPU context allocation</i>) or a device-specific context (<i>device context allocation</i>).

A GPU context allocation allows GPUs to store context state from DMA buffers that are preempted in the middle of their execution. Drivers create allocations associated with a GPU context to save its state when it is necessary. The operating system ensures that the context allocation is resident before a command from this context is placed in the GPU's hardware execution queue.
The context will stay resident until a command from another context is placed in the hardware execution queue. 

In addition, the operating system  supports lazy GPU context switching by assuming that hardware context state is retained on the GPU after completing a command that belongs to the context. In this way, contexts are only switched on the GPU when a command from a different context is submitted to the hardware queue.


<h3><a id="GPU_context_allocations"></a><a id="gpu_context_allocations"></a><a id="GPU_CONTEXT_ALLOCATIONS"></a>GPU context allocations</h3>
GPU context allocations can only be made for non-system contexts. The display miniport driver creates these contexts by calling <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>. To create a non-system context, the driver sets the <b>SystemContext</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561037">DXGK_CREATECONTEXTFLAGS</a> structure to zero, and passes a pointer to this structure in the <i>pCreateContext</i> parameter.

A device context allocation   follows a similar model, except that it will remain resident for any context that belongs to the device that it’s associated with. This model allows drivers to use GPU context allocations for storing GPU context save area (CSA) data and to use device context allocations for storing page table data.

<h3><a id="Device_context_allocations"></a><a id="device_context_allocations"></a><a id="DEVICE_CONTEXT_ALLOCATIONS"></a>Device context allocations</h3>
Device context allocations can only be made for non-system devices. The display miniport driver creates these devices by calling <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>. To create a non-system device, the driver sets the <b>Flags.SystemDevice</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561039">DXGK_CREATEDEVICEFLAGS</a>  structure to zero, and passes a pointer to this structure in the <i>pCreateDevice</i> parameter.

The display miniport driver  calls <a href="https://msdn.microsoft.com/f613e019-0b6d-43fc-a802-a6cd3803a00d">DxgkCbDestroyContextAllocation</a> to free the context resources that were allocated through <i>DxgkCbCreateContextAllocation</i>.

<h3><a id="virtual_addresses"></a><a id="VIRTUAL_ADDRESSES"></a>Virtual addresses for destination context allocations</h3>
To ensure that the operating system sets a valid (non-<b>NULL</b>) virtual address for the destination context allocation (<b>InitContextResource</b>-&gt;<b>Destination</b>-&gt;<b>VirtualAddress</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a> structure), when the display miniport driver calls <i>DxgkCbCreateContextAllocation</i> it must:<ul>
<li>Set the <b>CpuVisible</b> and <b>Protected</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560966">DXGK_ALLOCATIONINFOFLAGS</a> structure.</li>
<li>Page in the allocation only to aperture segments by setting  the <b>SupportedSegmentSet</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451242">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure.</li>
</ul>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451242">DXGKARGCB_CREATECONTEXTALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560966">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561037">DXGK_CREATECONTEXTFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561039">DXGK_CREATEDEVICEFLAGS</a>



<a href="https://msdn.microsoft.com/f613e019-0b6d-43fc-a802-a6cd3803a00d">DxgkCbDestroyContextAllocation</a>



<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>
 

 

