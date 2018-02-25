---
UID: NS:dxgiddi.DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
title: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
author: windows-driver-content
description: Describes multiplane overlay allocations that content is copied to and from.
old-location: display\dxgiddicb_present_multiplane_overlay.htm
old-project: display
ms.assetid: 4f240d75-e7c5-4ba2-a0f0-22280aaaefd6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, B, C, D, DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY, DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY structure [Display Devices], E, G, I, L, M, N, O, P, R, S, T, U, V, X, Y, _, display.dxgiddicb_present_multiplane_overlay, dxgiddi/DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
product: Windows
targetos: Windows
req.typenames: DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY
---

# DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY structure


## -description


Describes multiplane overlay allocations that content is copied to and from.


## -syntax


````
typedef struct DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY {
  void                                       *pDXGIContext;
  HANDLE                                     hContext;
  UINT                                       BroadcastContextCount;
  HANDLE                                     BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  DWORD                                      AllocationInfoCount;
  DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO AllocationInfo[DXGI_DDI_MAX_MULTIPLANE_OVERLAY_ALLOCATIONS];
} DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY;
````


## -struct-fields




### -field pDXGIContext

[in] A handle to the Microsoft DirectX Graphics Infrastructure (DXGI)  context. This handle is opaque to the driver. The driver should assign the handle from the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-_dxgi_ddi_arg_presentmultiplaneoverlay.md">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a> structure that the driver received in a call to its <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb.md">pfnPresentMultiplaneOverlay (DXGI)</a> function to this member.


### -field hContext

[in] A handle to the context that the driver submits the copy operation to. The user-mode display driver previously created this context by calling the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function.


### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.


### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current present operation to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current present operation to. 

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure when its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the user-mode display driver presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context. 


### -field AllocationInfoCount

[in] The number of allocations in the array that the <b>AllocationInfo</b> member specifies. The maximum number is 16, the value of the <b>DXGI_DDI_MAX_MULTIPLANE_OVERLAY_ALLOCATIONS</b> constant.


### -field AllocationInfo

An array of structures of type <a href="..\dxgiddi\ns-dxgiddi-dxgiddi_multiplane_overlay_allocation_info.md">DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO</a> that specify info about the multiplane overlay allocations.


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-_dxgi_ddi_arg_presentmultiplaneoverlay.md">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgiddi_multiplane_overlay_allocation_info.md">DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO</a>



<a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb.md">pfnPresentMultiplaneOverlay (DXGI)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

