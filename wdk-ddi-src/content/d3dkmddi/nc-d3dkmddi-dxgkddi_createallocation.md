---
UID: NC:d3dkmddi.DXGKDDI_CREATEALLOCATION
title: DXGKDDI_CREATEALLOCATION (d3dkmddi.h)
description: Learn more about the DxgkDdiCreateAllocation function.
ms.date: 08/19/2024
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - DXGKDDI_CREATEALLOCATION
 - d3dkmddi/DXGKDDI_CREATEALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CREATEALLOCATION
---

# DXGKDDI_CREATEALLOCATION callback function

## -description

The kernel-mode display driver's (KMD) **DxgkDdiCreateAllocation** function creates allocations of system or video memory.

## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCreateAllocation [in/out]

A pointer to a [**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md) structure that contains information for creating allocations.

## -returns

**DxgkDdiCreateAllocation** returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | **DxgkDdiCreateAllocation** successfully created the allocation. |
| **STATUS_INVALID_PARAMETER** | The passed parameters contained errors that prevented **DxgkDdiCreateAllocation** from completing. |
| **STATUS_NO_MEMORY** | **DxgkDdiCreateAllocation**  could not allocate memory that was required for it to complete. |
| **STATUS_GRAPHICS_DRIVER_MISMATCH** | The KMD isn't compatible with the user-mode display driver (UMD) that initiated the call to **DxgkDdiCreateAllocation**. |

## -remarks

After the UMD calls [**pfnAllocateCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb.md), *Dxgkrnl* calls KMD's **DxgkDdiCreateAllocation** function to create the allocations. The KMD must interpret the private data (in the **pPrivateDriverData** member of the [**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md) structure for each allocation) that is passed from the UMD and must determine the list of parameters that are required to create each allocation through the video memory manager. For more information about how the KMD supplies these parameters to the video memory manager, see [Specifying Segments When Creating Allocations](/windows-hardware/drivers/display/specifying-segments-when-creating-allocations).

The KMD must return an allocation handle, which is typically a pointer to a private driver data structure that contains information about the allocation. The UMD can call the [**DxgkCbGetHandleData**](nc-d3dkmddi-dxgkcb_gethandledata.md) function anytime to retrieve the private data for an allocation handle. Therefore, the KMD isn't required to maintain a private allocation handle table. In fact, we strongly discourage private handle tables because they could become stale or out of sync with the DirectX graphics kernel subsystem in display-mode-switch scenarios such as fast user switch, hot unplug, and so on.

The user-mode display driver assigns an allocation to either a resource or a device. To determine whether the allocation belongs to a resource, the display miniport driver can check whether the **Resource** bit-field flag is set in the **Flags** member of the [**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md) structure that the **pCreateAllocation** parameter of **DxgkDdiCreateAllocation** points to. If the allocation belongs to a resource, the display miniport driver can (but is not required to) return a resource handle, which is typically a pointer to a private driver data structure that describes the resource. If the DirectX graphics kernel subsystem calls **DxgkDdiCreateAllocation** to create an additional allocation for an existing resource, the **hResource** member of DXGKARG_CREATEALLOCATION contains the handle that was returned by the previous **DxgkDdiCreateAllocation** call for that resource. If necessary, the display miniport driver can change the resource handle during a call to **DxgkDdiCreateAllocation**.

If the user-mode display driver places a resource handle in a command buffer, the display miniport driver can retrieve the private data by calling [**DxgkCbGetHandleData**](nc-d3dkmddi-dxgkcb_gethandledata.md). The display miniport driver can also enumerate all of the resource's child allocations by calling the [**DxgkCbEnumHandleChildren**](nc-d3dkmddi-dxgkcb_enumhandlechildren.md) function.

Beginning with Windows 7, if a display miniport driver processes a call to the **DxgkDdiCreateAllocation** function to create allocations for GDI hardware acceleration, the driver should set the size of the allocation (including the pitch value for CPU visible allocations), **pCreateAllocation**->**pAllocationInfo**->**Size**.

The resources that are created in the **DxgkDdiCreateAllocation** call belong to the adapter and not to the device. The display miniport driver should not reference the device data anywhere within the private allocation and resource data structures. Because of surface sharing, a resource might be in use after the destruction of the device that the user-mode display driver created the resource from.

**DxgkDdiCreateAllocation** should be made pageable.

### Allocating history buffers

Starting in Windows 8.1, when **DxgkDdiCreateAllocation** is called, the KMD can set the [**DXGK_ALLOCATIONINFOFLAGS**](ns-d3dkmddi-_dxgk_allocationinfoflags.md).**HistoryBuffer** member to indicate that the user-mode driver can manage the creation and destruction of history buffers.

## -see-also

[**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md)

[**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DXGK_ALLOCATIONINFOFLAGS**](ns-d3dkmddi-_dxgk_allocationinfoflags.md)

[**DxgkCbEnumHandleChildren**](nc-d3dkmddi-dxgkcb_enumhandlechildren.md)

[**DxgkCbGetHandleData**](nc-d3dkmddi-dxgkcb_gethandledata.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**pfnAllocateCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb.md)
