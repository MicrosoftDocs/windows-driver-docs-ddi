---
UID: NC:d3dkmddi.DXGKCB_CREATECONTEXTALLOCATION
title: DXGKCB_CREATECONTEXTALLOCATION (d3dkmddi.h)
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to allocate a GPU context or device-specific context.
old-location: display\dxgkcbcreatecontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_CREATECONTEXTALLOCATION callback function"]
ms.keywords: DXGKCB_CREATECONTEXTALLOCATION, DXGKCB_CREATECONTEXTALLOCATION callback, DxgkCbCreateContextAllocation, DxgkCbCreateContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbCreateContextAllocation, display.dxgkcbcreatecontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_CREATECONTEXTALLOCATION
 - d3dkmddi/DXGKCB_CREATECONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_CREATECONTEXTALLOCATION
---

# DXGKCB_CREATECONTEXTALLOCATION callback function

## -description

**DXGKCB_CREATECONTEXTALLOCATION** allocates a GPU context or device-specific context.

## -parameters

### -param ContextAllocation

[in/out] A pointer to a [**DXGKARGCB_CREATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md) structure that specifies the attributes of the context to be allocated.

## -returns

**DXGKCB_CREATECONTEXTALLOCATION** returns **STATUS_SUCCESS** if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

Starting with WDDM 1.2, display miniport drivers can allocate a GPU-specific context (**GPU context allocation**) or a device-specific context (**device context allocation**).

A GPU context allocation allows GPUs to store context state from DMA buffers that are preempted in the middle of their execution. Drivers create allocations associated with a GPU context to save its state when it is necessary. The operating system ensures that the context allocation is resident before a command from this context is placed in the GPU's hardware execution queue. The context will stay resident until a command from another context is placed in the hardware execution queue.

In addition, the operating system supports lazy GPU context switching by assuming that hardware context state is retained on the GPU after completing a command that belongs to the context. In this way, contexts are only switched on the GPU when a command from a different context is submitted to the hardware queue.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md) and then call **DxgkCbCreateContextAllocation** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

### GPU context allocations

GPU context allocations can only be made for non-system contexts. The display miniport driver creates these contexts by calling [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md). To create a non-system context, the driver sets the **SystemContext** member of a [**DXGK_CREATECONTEXTFLAGS**](ns-d3dkmddi-_dxgk_createcontextflags.md) structure to zero, and passes a pointer to this structure in the **pCreateContext** parameter.

A device context allocation follows a similar model, except that it will remain resident for any context that belongs to the device that it’s associated with. This model allows drivers to use GPU context allocations for storing GPU context save area (CSA) data and to use device context allocations for storing page table data.

### Device context allocations

Device context allocations can only be made for non-system devices. The display miniport driver creates these devices by calling [**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md). To create a non-system device, the driver sets the **Flags.SystemDevice** member of a [**DXGK_CREATEDEVICEFLAGS**](ns-d3dkmddi-_dxgk_createdeviceflags.md) structure to zero, and passes a pointer to this structure in the **pCreateDevice** parameter.

The display miniport driver calls [**DXGKCB_DESTROYCONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_destroycontextallocation.md) to free the context resources that were allocated through **DxgkCbCreateContextAllocation**.

### Virtual addresses for destination context allocations

To ensure that the operating system sets a valid (non-NULL) virtual address for the destination context allocation (**InitContextResource->Destination->VirtualAddress** member of the [**DXGKARG_BUILDPAGINGBUFFER**](ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md) structure), when the display miniport driver calls **DxgkCbCreateContextAllocation** it must:

* Set the **CpuVisible** and **Protected** members of the [**DXGK_ALLOCATIONINFOFLAGS**](ns-d3dkmddi-_dxgk_allocationinfoflags.md) structure.
* Page in the allocation only to aperture segments by setting  the **SupportedSegmentSet** member of the [**DXGKARGCB_CREATECONTEXTALLOCATION**](d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation.md) structure.

## -see-also

[**DXGK_ALLOCATIONINFOFLAGS**](ns-d3dkmddi-_dxgk_allocationinfoflags.md)

[**DXGK_CREATECONTEXTFLAGS**](ns-d3dkmddi-_dxgk_createcontextflags.md)

[**DXGK_CREATEDEVICEFLAGS**](ns-d3dkmddi-_dxgk_createdeviceflags.md)

[**DXGKARG_BUILDPAGINGBUFFER**](ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md)

[**DXGKARGCB_CREATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md)

[**DXGKCB_DESTROYCONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_destroycontextallocation.md)

[**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md)

[**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
