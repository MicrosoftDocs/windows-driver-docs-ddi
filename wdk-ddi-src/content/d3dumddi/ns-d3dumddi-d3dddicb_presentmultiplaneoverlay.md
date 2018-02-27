---
UID: NS:d3dumddi.D3DDDICB_PRESENTMULTIPLANEOVERLAY
title: D3DDDICB_PRESENTMULTIPLANEOVERLAY
author: windows-driver-content
description: Describes multiplane overlay allocations that content is copied to and from.
old-location: display\d3dddicb_presentmultiplaneoverlay.htm
old-project: display
ms.assetid: 4161418c-4f56-4daf-bf3d-e76899ccd1b2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDICB_PRESENTMULTIPLANEOVERLAY, D3DDDICB_PRESENTMULTIPLANEOVERLAY structure [Display Devices], d3dumddi/D3DDDICB_PRESENTMULTIPLANEOVERLAY, display.d3dddicb_presentmultiplaneoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
apiname:
-	D3DDDICB_PRESENTMULTIPLANEOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_PRESENTMULTIPLANEOVERLAY
---

# D3DDDICB_PRESENTMULTIPLANEOVERLAY structure


## -description


Describes multiplane overlay allocations that content is copied to and from.


## -syntax


````
typedef struct D3DDDICB_PRESENTMULTIPLANEOVERLAY {
  HANDLE                            hContext;
  UINT                              BroadcastContextCount;
  HANDLE                            BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  UINT                              AllocationInfoCount;
  D3DDDI_MULTIPLANE_ALLOCATION_INFO AllocationInfo[D3DDDI_MAX_MULTIPLANE_OVERLAY_ALLOCATIONS];
} D3DDDICB_PRESENTMULTIPLANEOVERLAY;
````


## -struct-fields




### -field hContext

[in] A handle to the context that the driver submits the copy operation to. The user-mode display driver previously created this context by calling the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function.


### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.


### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current present operation to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current present operation to. 

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure when its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the user-mode display driver presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context. 


### -field AllocationInfoCount

[in] The number of allocations in the array that the <b>AllocationInfo</b> member specifies. The maximum number is 16, the value of the <b>D3DDDI_MAX_MULTIPLANE_OVERLAY_ALLOCATIONS</b> constant.


### -field AllocationInfo

An array of structures of type <a href="..\d3dumddi\ns-d3dumddi-d3dddi_multiplane_overlay_allocation_info.md">D3DDDI_MULTIPLANE_ALLOCATION_INFO</a> that specify info about the multiplane overlay allocations.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="..\d3dumddi\ns-d3dumddi-d3dddi_multiplane_overlay_allocation_info.md">D3DDDI_MULTIPLANE_ALLOCATION_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_PRESENTMULTIPLANEOVERLAY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

