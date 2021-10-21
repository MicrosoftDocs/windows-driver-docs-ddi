---
UID: NC:d3dkmddi.DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
title: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE (d3dkmddi.h)
description: DxgkCbReserveGpuVirtualAddressRange allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkcbreservegpuvirtualaddressrange.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback function"]
ms.keywords: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE, DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback, DxgkCbReserveGpuVirtualAddressRange, DxgkCbReserveGpuVirtualAddressRange callback function [Display Devices], d3dkmddi/DxgkCbReserveGpuVirtualAddressRange, display.dxgkcbreservegpuvirtualaddressrange, dispmprt/DxgkCbReserveGpuVirtualAddressRange
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
 - d3dkmddi/DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
 - d3dkmddi.h
api_name:
 - DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
product:
 - Windows
---

# DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback function

## -description

A kernel-mode display miniport driver can call **DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE** to reserve a graphics processing unit (GPU) virtual address range during creation of a process.

## -parameters

### -param hAdapter [in]

A handle to the display adapter.

### -param pArgs [in/out]

A [**DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE**](ns-d3dkmddi-_dxgkargcb_reservegpuvirtualaddressrange.md) structure that describes the operation.

## -returns

**DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE** returns **STATUS_SUCCESS** if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

Reserving the GPU virtual address range is only possible during process creation (i.e. within the call to [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)) and is invalid at any other time.

Reservation is possible on both a regular process as well as the system process where the system device and context lives.

The first entry in the root page table (page table entry index 0) will always be initialized as invalid by the video memory manager and the driver reservations will start from page table entry index 1. Driver reservation must always be an exact multiple of virtual address space, covered by leaf page table, as the specific page table entry can’t be shared between the video memory manager and the kernel-mode driver. Page table entries reserved by the driver will be initialized as *invalid* by the video memory manager and may be overwritten by the driver to reference an internally allocated page table managed by the driver. The video memory manager will update the reserved page table entries as invalid every time the corresponding page table becomes resident.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE**](ns-d3dkmddi-_dxgkargcb_reservegpuvirtualaddressrange.md) and then call **DxgkCbReserveGpuVirtualAddressRange** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE**](ns-d3dkmddi-_dxgkargcb_reservegpuvirtualaddressrange.md)

[**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
