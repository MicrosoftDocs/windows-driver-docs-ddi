---
UID: NS:dxgiddi.DXGIDDICB_PRESENT
title: DXGIDDICB_PRESENT
author: windows-driver-content
description: The DXGIDDICB_PRESENT structure describes allocations that content is copied to and from.
old-location: display\dxgiddicb_present.htm
old-project: display
ms.assetid: 1d766004-c6bb-40c6-ad5d-d2bea53649d3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGIDDICB_PRESENT, DXGIDDICB_PRESENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGIDDICB_PRESENT
req.alt-loc: dxgiddi.h
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
req.typenames: DXGIDDICB_PRESENT
---

# DXGIDDICB_PRESENT structure



## -description
The DXGIDDICB_PRESENT structure describes allocations that content is copied to and from. 



## -syntax

````
typedef struct DXGIDDICB_PRESENT {
  D3DKMT_HANDLE hSrcAllocation;
  D3DKMT_HANDLE hDstAllocation;
  void          *pDXGIContext;
  HANDLE        hContext;
  UINT          BroadcastContextCount;
  HANDLE        BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
} DXGIDDICB_PRESENT;
````


## -struct-fields

### -field hSrcAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation. The Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns this handle. Therefore, the user-mode display driver should use this handle to copy content from.


### -field hDstAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the destination allocation. <b>hDstAllocation</b> can be zero if the destination is unknown; kernel mode will determine the destination just before sending the hardware command stream through DMA to the graphics processor.


### -field pDXGIContext

[in] A handle to the Microsoft DirectX Graphics Infrastructure (DXGI) context. This handle is opaque to the driver. The driver should assign the handle from the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present.md">DXGI_DDI_ARG_PRESENT</a> structure that the driver received in a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function to this member. 


### -field hContext

[in] A handle to the context that the driver submits the copy operation to. The user-mode display driver previously created this context by calling the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function. 


### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.


### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current present operation to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current present operation to. 

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure when its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the user-mode display driver presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present.md">DXGI_DDI_ARG_PRESENT</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
</dt>
<dt>
<a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGIDDICB_PRESENT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

