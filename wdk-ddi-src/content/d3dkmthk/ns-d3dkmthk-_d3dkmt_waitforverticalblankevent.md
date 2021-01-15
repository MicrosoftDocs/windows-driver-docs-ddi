---
UID: NS:d3dkmthk._D3DKMT_WAITFORVERTICALBLANKEVENT
title: _D3DKMT_WAITFORVERTICALBLANKEVENT (d3dkmthk.h)
description: The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur.
old-location: display\d3dkmt_waitforverticalblankevent.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_WAITFORVERTICALBLANKEVENT structure"]
ms.keywords: D3DKMT_WAITFORVERTICALBLANKEVENT, D3DKMT_WAITFORVERTICALBLANKEVENT structure [Display Devices], OpenGL_Structs_1072adb2-825b-4fee-a84a-b958e3d2e4d4.xml, _D3DKMT_WAITFORVERTICALBLANKEVENT, d3dkmthk/D3DKMT_WAITFORVERTICALBLANKEVENT, display.d3dkmt_waitforverticalblankevent
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
req.typenames: D3DKMT_WAITFORVERTICALBLANKEVENT
f1_keywords:
 - _D3DKMT_WAITFORVERTICALBLANKEVENT
 - d3dkmthk/_D3DKMT_WAITFORVERTICALBLANKEVENT
 - D3DKMT_WAITFORVERTICALBLANKEVENT
 - d3dkmthk/D3DKMT_WAITFORVERTICALBLANKEVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_WAITFORVERTICALBLANKEVENT
 - D3DKMT_WAITFORVERTICALBLANKEVENT
---

# _D3DKMT_WAITFORVERTICALBLANKEVENT structure


## -description

The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur.

## -struct-fields

### -field hAdapter

[in] A handle to the adapter.

### -field hDevice

[in] A handle to the display device. This member is optionally specified. However, if the OpenGL ICD specifies the display device, the kernel is given more optimization opportunities with regard to power usage.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the VidPN source.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforverticalblankevent">D3DKMTWaitForVerticalBlankEvent</a>

