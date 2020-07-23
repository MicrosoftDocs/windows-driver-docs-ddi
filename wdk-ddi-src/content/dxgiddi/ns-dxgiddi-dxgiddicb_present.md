---
UID: NS:dxgiddi.DXGIDDICB_PRESENT
title: DXGIDDICB_PRESENT (dxgiddi.h)
description: The DXGIDDICB_PRESENT structure describes allocations that content is copied to and from.
old-location: display\dxgiddicb_present.htm
tech.root: display
ms.assetid: 1d766004-c6bb-40c6-ad5d-d2bea53649d3
ms.date: 05/10/2018
keywords: ["DXGIDDICB_PRESENT structure"]
ms.keywords: DXGIDDICB_PRESENT, DXGIDDICB_PRESENT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_932d6171-c487-44f6-834e-5d57b3e14515.xml, display.dxgiddicb_present, dxgiddi/DXGIDDICB_PRESENT
f1_keywords:
 - "dxgiddi/DXGIDDICB_PRESENT"
 - "DXGIDDICB_PRESENT"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxgiddi.h
api_name:
- DXGIDDICB_PRESENT
targetos: Windows
req.typenames: DXGIDDICB_PRESENT
---

# DXGIDDICB_PRESENT structure


## -description


The DXGIDDICB_PRESENT structure describes allocations that content is copied to and from. 


## -struct-fields




### -field hSrcAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation. The Microsoft Direct3D runtime's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function returns this handle. Therefore, the user-mode display driver should use this handle to copy content from.


### -field hDstAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the destination allocation. <b>hDstAllocation</b> can be zero if the destination is unknown; kernel mode will determine the destination just before sending the hardware command stream through DMA to the graphics processor.


### -field pDXGIContext

[in] A handle to the Microsoft DirectX Graphics Infrastructure (DXGI) context. This handle is opaque to the driver. The driver should assign the handle from the <b>pDXGIContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a> structure that the driver received in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> function to this member. 


### -field hContext

[in] A handle to the context that the driver submits the copy operation to. The user-mode display driver previously created this context by calling the <a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> function. 


### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.


### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current present operation to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current present operation to. 

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure when its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the user-mode display driver presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context. 


### -field BroadcastSrcAllocation

 
Allocations which content will be presented.

### -field BroadcastDstAllocation

If non-zero, represents the destination allocations of the present.


### -field PrivateDriverDataSize

 
Private driver data size in bytes.

### -field pPrivateDriverData

 
Private driver data to pass to DxgiPresent.

### -field bOptimizeForComposition

 
DWM is involved in composition.

### -field SyncIntervalOverrideValid

Override app sync interval is valid. 


### -field SyncIntervalOverride

 
Override app sync interval.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_present">DXGI_DDI_ARG_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a>



<a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_presentcb">pfnPresentCbDXGI</a>
 

 

