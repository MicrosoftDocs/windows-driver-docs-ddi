---
UID: NC:d3dkmddi.DXGKDDI_CREATEALLOCATION
title: DXGKDDI_CREATEALLOCATION (d3dkmddi.h)
description: The DxgkDdiCreateAllocation function creates allocations of system or video memory.
old-location: display\dxgkddicreateallocation.htm
ms.assetid: a28287d6-4dfa-4db4-92df-bbcd9379a5b2
ms.date: 05/10/2018
ms.keywords: DXGKDDI_CREATEALLOCATION, DXGKDDI_CREATEALLOCATION callback, DmFunctions_fa00d14b-b5f1-4dde-8283-cc7b71911f76.xml, DxgkDdiCreateAllocation, DxgkDdiCreateAllocation callback function [Display Devices], d3dkmddi/DxgkDdiCreateAllocation, display.dxgkddicreateallocation
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiCreateAllocation"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiCreateAllocation
product:
 - Windows
---

# DXGKDDI_CREATEALLOCATION callback function

## -description

The <i>DxgkDdiCreateAllocation</i> function creates allocations of system or video memory.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pCreateAllocation

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a> structure that contains information for creating allocations.

## -returns

<i>DxgkDdiCreateAllocation</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | [DxgkDdiCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation) successfully created the allocation. | 
| **STATUS_INVALID_PARAMETER** | Parameters that were passed to [DxgkDdiCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation) contained errors that prevented it from completing. | 
| **STATUS_NO_MEMORY** | [DxgkDdiCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation)  could not allocate memory that was required for it to complete. |
| **STATUS_GRAPHICS_DRIVER_MISMATCH** | The display miniport driver is not compatible with the user-mode display driver that initiated the call to [DxgkDdiCreateAllocation](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation). |

## -remarks

After the user-mode display driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function, the DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiCreateAllocation</i> function to create the allocations. The display miniport driver must interpret the private data (in the <b>pPrivateDriverData</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structure for each allocation) that is passed from the user-mode display driver and must determine the list of parameters that are required to create each allocation through the video memory manager. For more information about how the display miniport driver supplies these parameters to the video memory manager, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/specifying-segments-when-creating-allocations">Specifying Segments When Creating Allocations</a>. 

The display miniport driver must return an allocation handle, which is typically a pointer to a private driver data structure that contains information about the allocation. The display miniport driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata">DxgkCbGetHandleData</a> function anytime to retrieve the private data for an allocation handle. Therefore, the display miniport driver is not required to maintain a private allocation handle table. In fact, we strongly discourage private handle tables because they could become stale or out of sync with the DirectX graphics kernel subsystem in display-mode-switch scenarios such as fast user switch, hot unplug, and so on.

The user-mode display driver assigns an allocation to either a resource or a device. To determine whether the allocation belongs to a resource, the display miniport driver can check whether the <b>Resource</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a> structure that the <i>pCreateAllocation</i> parameter of <i>DxgkDdiCreateAllocation</i> points to. If the allocation belongs to a resource, the display miniport driver can (but is not required to) return a resource handle, which is typically a pointer to a private driver data structure that describes the resource. If the DirectX graphics kernel subsystem calls <i>DxgkDdiCreateAllocation</i> to create an additional allocation for an existing resource, the <b>hResource</b> member of DXGKARG_CREATEALLOCATION contains the handle that was returned by the previous <i>DxgkDdiCreateAllocation</i> call for that resource. If necessary, the display miniport driver can change the resource handle during a call to <i>DxgkDdiCreateAllocation</i>. 

If the user-mode display driver places a resource handle in a command buffer, the display miniport driver can retrieve the private data by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata">DxgkCbGetHandleData</a>. The display miniport driver can also enumerate all of the resource's child allocations by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_enumhandlechildren">DxgkCbEnumHandleChildren</a> function.

Beginning with Windows 7, if a display miniport driver processes a call to the <i>DxgkDdiCreateAllocation</i> function to create allocations for GDI hardware acceleration, the driver should set the size of the allocation (including the pitch value for CPU visible allocations), <i>pCreateAllocation</i>-><b>pAllocationInfo</b>-><b>Size</b>.

The resources that are created in the <i>DxgkDdiCreateAllocation</i> call belong to the adapter and not to the device. The display miniport driver should not reference the device data anywhere within the private allocation and resource data structures. Because of surface sharing, a resource might be in use after the destruction of the device that the user-mode display driver created the resource from. 

<i>DxgkDdiCreateAllocation</i> should be made pageable.

### Allocating history buffers

Starting in Windows 8.1, when <i>DxgkDdiCreateAllocation</i> is called, the display miniport driver can set the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a>.<b>HistoryBuffer</b> member to indicate that the user-mode driver can manage the creation and destruction of history buffers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_enumhandlechildren">DxgkCbEnumHandleChildren</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata">DxgkCbGetHandleData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a>

