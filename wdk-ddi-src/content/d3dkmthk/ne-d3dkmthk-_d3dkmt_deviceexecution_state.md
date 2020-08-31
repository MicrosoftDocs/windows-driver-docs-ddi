---
UID: NE:d3dkmthk._D3DKMT_DEVICEEXECUTION_STATE
title: _D3DKMT_DEVICEEXECUTION_STATE (d3dkmthk.h)
description: Contains values that indicate the execution status for a device.
old-location: display\d3dkmt_deviceexecution_state.htm
ms.assetid: 31935433-6fa4-4d1a-9ad4-879353102e71
ms.date: 05/10/2018
keywords: ["D3DKMT_DEVICEEXECUTION_STATE enumeration"]
ms.keywords: D3DKMT_DEVICEEXECUTION_ACTIVE, D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT, D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT, D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY, D3DKMT_DEVICEEXECUTION_HUNG, D3DKMT_DEVICEEXECUTION_RESET, D3DKMT_DEVICEEXECUTION_STATE, D3DKMT_DEVICEEXECUTION_STATE enumeration [Display Devices], D3DKMT_DEVICEEXECUTION_STOPPED, OpenGL_Structs_35637d1a-f40f-49f5-b774-777e02f22b68.xml, _D3DKMT_DEVICEEXECUTION_STATE, d3dkmthk/, d3dkmthk/D3DKMT_DEVICEEXECUTION_ACTIVE, d3dkmthk/D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT, d3dkmthk/D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT, d3dkmthk/D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY, d3dkmthk/D3DKMT_DEVICEEXECUTION_HUNG, d3dkmthk/D3DKMT_DEVICEEXECUTION_RESET, d3dkmthk/D3DKMT_DEVICEEXECUTION_STATE, d3dkmthk/D3DKMT_DEVICEEXECUTION_STOPPED, display.d3dkmt_deviceexecution_state
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DEVICEEXECUTION_STATE
f1_keywords:
 - _D3DKMT_DEVICEEXECUTION_STATE
 - d3dkmthk/_D3DKMT_DEVICEEXECUTION_STATE
 - D3DKMT_DEVICEEXECUTION_STATE
 - d3dkmthk/D3DKMT_DEVICEEXECUTION_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_DEVICEEXECUTION_STATE
---

# _D3DKMT_DEVICEEXECUTION_STATE enumeration


## -description

The <b>D3DKMT_DEVICEEXECUTION_STATE</b> enumeration type contains values that indicate the execution status for a device.

## -enum-fields

### -field D3DKMT_DEVICEEXECUTION_ACTIVE

The device is actively executing.

### -field D3DKMT_DEVICEEXECUTION_RESET

The device is reset.

### -field D3DKMT_DEVICEEXECUTION_HUNG

The device is hung. The device is unable to continue.

### -field D3DKMT_DEVICEEXECUTION_STOPPED

      The device is stopped.

### -field D3DKMT_DEVICEEXECUTION_ERROR_OUTOFMEMORY

Even after the video memory manager split the DMA buffer, the video memory manager could not page-in all of the required allocations into video memory at the same time. The device is unable to continue.

### -field D3DKMT_DEVICEEXECUTION_ERROR_DMAFAULT

The display miniport driver reported a fault while processing a DMA buffer for the device. The device is unable to continue.

### -field D3DKMT_DEVICEEXECUTION_ERROR_DMAPAGEFAULT

The display miniport driver reported a page fault while processing a DMA buffer for the device. The device is unable to continue.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getdevicestate">D3DKMT_GETDEVICESTATE</a>

