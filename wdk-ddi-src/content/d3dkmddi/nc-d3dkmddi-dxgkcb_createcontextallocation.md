---
UID: NC:d3dkmddi.DXGKCB_CREATECONTEXTALLOCATION
title: DXGKCB_CREATECONTEXTALLOCATION
author: windows-driver-content
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to allocate a GPU context or device-specific context.
old-location: display\dxgkcbcreatecontextallocation.htm
old-project: display
ms.assetid: b6b142a4-20eb-4368-bd7f-8a25f4fe48ca
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbCreateContextAllocation
req.alt-loc: D3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_CREATECONTEXTALLOCATION callback



## -description
Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to allocate a GPU context or device-specific context.



## -prototype

````
DXGKCB_CREATECONTEXTALLOCATION DxgkCbCreateContextAllocation;

NTSTATUS APIENTRY CALLBACK* DxgkCbCreateContextAllocation(
  _Inout_ DXGKARGCB_CREATECONTEXTALLOCATION *ContextAllocation
)
{ ... }
````


## -parameters

### -param ContextAllocation [in, out]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure that specifies the attributes of the context to be allocated.


## -returns
<i>DxgkCbCreateContextAllocation</i> returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
Starting with WDDM 1.2, display miniport drivers can allocate a GPU-specific context (<i>GPU context allocation</i>) or a device-specific context (<i>device context allocation</i>).

A GPU context allocation allows GPUs to store context state from DMA buffers that are preempted in the middle of their execution. Drivers create allocations associated with a GPU context to save its state when it is necessary. The operating system ensures that the context allocation is resident before a command from this context is placed in the GPU's hardware execution queue.
The context will stay resident until a command from another context is placed in the hardware execution queue. 

In addition, the operating system  supports lazy GPU context switching by assuming that hardware context state is retained on the GPU after completing a command that belongs to the context. In this way, contexts are only switched on the GPU when a command from a different context is submitted to the hardware queue.


GPU context allocations can only be made for non-system contexts. The display miniport driver creates these contexts by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>. To create a non-system context, the driver sets the <b>SystemContext</b> member of a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createcontextflags.md">DXGK_CREATECONTEXTFLAGS</a> structure to zero, and passes a pointer to this structure in the <i>pCreateContext</i> parameter.

A device context allocation   follows a similar model, except that it will remain resident for any context that belongs to the device that it’s associated with. This model allows drivers to use GPU context allocations for storing GPU context save area (CSA) data and to use device context allocations for storing page table data.

Device context allocations can only be made for non-system devices. The display miniport driver creates these devices by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>. To create a non-system device, the driver sets the <b>Flags.SystemDevice</b> member of a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createdeviceflags.md">DXGK_CREATEDEVICEFLAGS</a>  structure to zero, and passes a pointer to this structure in the <i>pCreateDevice</i> parameter.

The display miniport driver  calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_destroycontextallocation.md">DxgkCbDestroyContextAllocation</a> to free the context resources that were allocated through <i>DxgkCbCreateContextAllocation</i>.

To ensure that the operating system sets a valid (non-<b>NULL</b>) virtual address for the destination context allocation (<b>InitContextResource</b>-&gt;<b>Destination</b>-&gt;<b>VirtualAddress</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a> structure), when the display miniport driver calls <i>DxgkCbCreateContextAllocation</i> it must:<ul>
<li>Set the <b>CpuVisible</b> and <b>Protected</b> members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a> structure.</li>
<li>Page in the allocation only to aperture segments by setting  the <b>SupportedSegmentSet</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure.</li>
</ul>



## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createcontextflags.md">DXGK_CREATECONTEXTFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createdeviceflags.md">DXGK_CREATEDEVICEFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_destroycontextallocation.md">DxgkCbDestroyContextAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_CREATECONTEXTALLOCATION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

