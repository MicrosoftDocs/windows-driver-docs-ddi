---
UID: NS:d3dumddi.D3DDDICB_PRESENTMULTIPLANEOVERLAY
title: D3DDDICB_PRESENTMULTIPLANEOVERLAY (d3dumddi.h)
description: Describes multiplane overlay allocations that content is copied to and from.
old-location: display\d3dddicb_presentmultiplaneoverlay.htm
tech.root: display
ms.assetid: 4161418c-4f56-4daf-bf3d-e76899ccd1b2
ms.date: 05/10/2018
keywords: ["D3DDDICB_PRESENTMULTIPLANEOVERLAY structure"]
ms.keywords: D3DDDICB_PRESENTMULTIPLANEOVERLAY, D3DDDICB_PRESENTMULTIPLANEOVERLAY structure [Display Devices], d3dumddi/D3DDDICB_PRESENTMULTIPLANEOVERLAY, display.d3dddicb_presentmultiplaneoverlay
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
targetos: Windows
req.typenames: D3DDDICB_PRESENTMULTIPLANEOVERLAY
f1_keywords:
 - D3DDDICB_PRESENTMULTIPLANEOVERLAY
 - d3dumddi/D3DDDICB_PRESENTMULTIPLANEOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDICB_PRESENTMULTIPLANEOVERLAY
---

# D3DDDICB_PRESENTMULTIPLANEOVERLAY structure


## -description

Describes multiplane overlay allocations that content is copied to and from.

## -struct-fields

### -field hContext

[in] A handle to the context that the driver submits the copy operation to. The user-mode display driver previously created this context by calling the <a href="/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> function.

### -field BroadcastContextCount

[in] The number of additional contexts in the array that the <b>BroadcastContext</b> member specifies.

### -field BroadcastContext

[in] An array of handles to the additional contexts to broadcast the current present operation to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of additional contexts that the user-mode display driver can broadcast the current present operation to. 

Broadcasting is supported only for flip operations. To broadcast a flip operation, the display miniport driver must support memory mapped I/O (MMIO)-based flips. To indicate support of MMIO flips, the display miniport driver sets the <b>FlipOnVSyncMmIo</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure when its <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function is called.

The original context that the <b>hContext</b> member specifies and that the user-mode display driver presents to is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the user-mode display driver sends the present operation to the owning context (<b>hContext</b>) and broadcasts to that one additional context.

### -field AllocationInfoCount

[in] The number of allocations in the array that the <b>AllocationInfo</b> member specifies. The maximum number is 16, the value of the <b>D3DDDI_MAX_MULTIPLANE_OVERLAY_ALLOCATIONS</b> constant.

### -field AllocationInfo

An array of structures of type <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddi_multiplane_overlay_allocation_info">D3DDDI_MULTIPLANE_ALLOCATION_INFO</a> that specify info about the multiplane overlay allocations.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddi_multiplane_overlay_allocation_info">D3DDDI_MULTIPLANE_ALLOCATION_INFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a>