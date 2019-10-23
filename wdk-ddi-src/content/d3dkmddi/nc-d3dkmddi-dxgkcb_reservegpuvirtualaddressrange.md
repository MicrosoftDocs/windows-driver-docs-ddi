---
UID: NC:d3dkmddi.DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
title: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE (d3dkmddi.h)
description: DxgkCbReserveGpuVirtualAddressRange allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkcbreservegpuvirtualaddressrange.htm
ms.assetid: 26A827F1-1094-4A7D-9C63-758925EE6273
ms.date: 05/10/2018
ms.keywords: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE, DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback, DxgkCbReserveGpuVirtualAddressRange, DxgkCbReserveGpuVirtualAddressRange callback function [Display Devices], d3dkmddi/DxgkCbReserveGpuVirtualAddressRange, display.dxgkcbreservegpuvirtualaddressrange, dispmprt/DxgkCbReserveGpuVirtualAddressRange
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkCbReserveGpuVirtualAddressRange"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
 - d3dkmddi.h
api_name:
 - DxgkCbReserveGpuVirtualAddressRange
product:
 - Windows
---

# DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback function

## -description

<b>DxgkCbReserveGpuVirtualAddressRange</b> allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process. Reserving the GPU virtual address range is only possible during process creation (i.e. within the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a>) and is invalid at any other time.

Reservation is possible on both regular process as well as the system process where the system device and context lives.


The first entry in the root page table (page table entry index 0) will always be initialized as invalid by the video memory manager and the driver reservations will start from page table entry  index 1. Driver reservation must always be an exact multiple of virtual address space, covered by leaf page table, as the specific page table entry can’t be shared between the video memory manager and the kernel mode driver. Page table entries reserved by the driver will be initialized as <i>invalid</i> by the video memory manager and may be overwritten by the driver to reference an internally allocated page table managed by the driver. The video memory manager will update the reserved page table entries as invalid every time the corresponding page table becomes resident.

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param pArgs

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_reservegpuvirtualaddressrange">DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</a> structure that describes the operation.

## -returns

      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_reservegpuvirtualaddressrange">DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a>

