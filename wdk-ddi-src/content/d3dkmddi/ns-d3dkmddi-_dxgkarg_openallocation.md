---
UID: NS:d3dkmddi._DXGKARG_OPENALLOCATION
title: "_DXGKARG_OPENALLOCATION"
author: windows-driver-content
description: The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open.
old-location: display\dxgkarg_openallocation.htm
old-project: display
ms.assetid: cddb85c7-137c-4ceb-b53c-170ce020cea1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_OPENALLOCATION, DXGKARG_OPENALLOCATION structure [Display Devices], DmStructs_442924a2-c130-487c-acdb-62a2b6e9f219.xml, _DXGKARG_OPENALLOCATION, d3dkmddi/DXGKARG_OPENALLOCATION, display.dxgkarg_openallocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available beginning with Windows Vista.
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
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_OPENALLOCATION
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_OPENALLOCATION
---

# _DXGKARG_OPENALLOCATION structure


## -description


The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open.


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that the <b>pOpenAllocation</b> member specifies, which represents the number of device-specific allocations to open.


### -field pOpenAllocation

[in/out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a> structures for the allocations to open.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. This block of private data is the same resource-specific data that is passed in the <b>pPrivateDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a> structure in the call to the <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function. The display miniport driver cannot modify this block of private data.


### -field PrivateDriverSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561981">DXGK_OPENALLOCATIONFLAGS</a> structure that identifies the operation to perform for allocations.


### -field SubresourceIndex

[in] Supported beginning with Windows 8.

An index into the resource for the render target surface.

The operating system specifies this member only if the display miniport driver supports <a href="https://msdn.microsoft.com/03db58e6-a6d5-4b6f-ba71-d22a985f9c57">GDI Hardware Acceleration</a>. Specifically, the display miniport driver must implement  the <a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> function and must create the device with the <b>GdiDevice</b> member set in <a href="https://msdn.microsoft.com/library/windows/hardware/ff557570">DXGKARG_CREATEDEVICE</a>.<b>Flags</b>.

If the value of <b>SubresourceIndex</b> is greater than the number of subresources in the allocation, the display miniport driver should return an error.


### -field SubresourceOffset

[out] Supported beginning with Windows 8.

The offset, in bytes, from the start of the allocation to the start of the subresource.


### -field Pitch

[out] Supported beginning with Windows 8.

The pitch, in bytes, of the allocation—that is, the distance, in bytes, to the start of the next row.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561981">DXGK_OPENALLOCATIONFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>
 

 

