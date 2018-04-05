---
UID: NC:d3dkmddi.DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
title: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
author: windows-driver-content
description: DxgkCbReserveGpuVirtualAddressRange allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkcbreservegpuvirtualaddressrange.htm
old-project: display
ms.assetid: 26A827F1-1094-4A7D-9C63-758925EE6273
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE, DxgkCbReserveGpuVirtualAddressRange, DxgkCbReserveGpuVirtualAddressRange callback function [Display Devices], d3dkmddi/DxgkCbReserveGpuVirtualAddressRange, display.dxgkcbreservegpuvirtualaddressrange, dispmprt/DxgkCbReserveGpuVirtualAddressRange
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
-	d3dkmddi.h
api_name:
-	DxgkCbReserveGpuVirtualAddressRange
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback


## -description


<b>DxgkCbReserveGpuVirtualAddressRange</b> allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process. Reserving the GPU virtual address range is only possible during process creation (i.e. within the call to <a href="https://msdn.microsoft.com/E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81">DxgkDdiCreateProcess</a>) and is invalid at any other time.

Reservation is possible on both regular process as well as the system process where the system device and context lives.


The first entry in the root page table (page table entry index 0) will always be initialized as invalid by the video memory manager and the driver reservations will start from page table entry  index 1. Driver reservation must always be an exact multiple of virtual address space, covered by leaf page table, as the specific page table entry can’t be shared between the video memory manager and the kernel mode driver. Page table entries reserved by the driver will be initialized as <i>invalid</i> by the video memory manager and may be overwritten by the driver to reference an internally allocated page table managed by the driver. The video memory manager will update the reserved page table entries as invalid every time the corresponding page table becomes resident.

  


## -parameters




### -param hAdapter [in]

A handle to the display adapter.


### -param pArgs [in, out]

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn906819">DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</a> structure that describes the operation.


## -returns




      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906819">DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</a>



<a href="https://msdn.microsoft.com/E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81">DxgkDdiCreateProcess</a>
 

 

