---
UID: NS:dxgiddi.DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
title: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
author: windows-driver-content
description: Describes multiplane overlay allocations that content is copied to and from.
old-location: display\dxgiddicb_present_multiplane_overlay.htm
tech.root: display
ms.assetid: 4f240d75-e7c5-4ba2-a0f0-22280aaaefd6
ms.date: 5/10/2018
ms.keywords: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY, DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY structure [Display Devices], display.dxgiddicb_present_multiplane_overlay, dxgiddi/DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
product:
- Windows
targetos: Windows
req.typenames: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
---

# DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY structure


## -description


Describes multiplane overlay allocations that content is copied to and from.


## -struct-fields




### -field pDXGIContext

[in] A handle to the Microsoft DirectX Graphics Infrastructure (DXGI)  context. This handle is opaque to the driver. The driver should assign the handle from the <b>pDXGIContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780280">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a> structure that the driver received in a call to its <a href="https://msdn.microsoft.com/C6EB96AC-0D5B-4D75-9B44-B1744F6A4360">pfnPresentMultiplaneOverlay (DXGI)</a> function to this member.


### -field hContext

[in] A handle to the context that the driver submits the copy operation to. The user-mode display driver previously created this context by calling the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function.


### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.


### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current present operation to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current present operation to. 

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a> structure when its <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the user-mode display driver presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context. 


### -field AllocationInfoCount

[in] The number of allocations in the array that the <b>AllocationInfo</b> member specifies. The maximum number is 16, the value of the <b>DXGI_DDI_MAX_MULTIPLANE_OVERLAY_ALLOCATIONS</b> constant.


### -field AllocationInfo

An array of structures of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh780276">DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO</a> that specify info about the multiplane overlay allocations.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780276">DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780280">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="https://msdn.microsoft.com/C6EB96AC-0D5B-4D75-9B44-B1744F6A4360">pfnPresentMultiplaneOverlay (DXGI)</a>
 

 

