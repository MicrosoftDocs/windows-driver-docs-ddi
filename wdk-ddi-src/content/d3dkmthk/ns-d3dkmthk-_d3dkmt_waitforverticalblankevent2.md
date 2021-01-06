---
UID: NS:d3dkmthk._D3DKMT_WAITFORVERTICALBLANKEVENT2
title: _D3DKMT_WAITFORVERTICALBLANKEVENT2 (d3dkmthk.h)
description: Describes parameters for multiple wait objects, including a vertical blank event. Supported starting with Windows 8.
old-location: display\d3dkmt_waitforverticalblankevent2.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_WAITFORVERTICALBLANKEVENT2 structure"]
ms.keywords: D3DKMT_WAITFORVERTICALBLANKEVENT2, D3DKMT_WAITFORVERTICALBLANKEVENT2 structure [Display Devices], _D3DKMT_WAITFORVERTICALBLANKEVENT2, d3dkmthk/D3DKMT_WAITFORVERTICALBLANKEVENT2, display.d3dkmt_waitforverticalblankevent2
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3DKMT_WAITFORVERTICALBLANKEVENT2
f1_keywords:
 - _D3DKMT_WAITFORVERTICALBLANKEVENT2
 - d3dkmthk/_D3DKMT_WAITFORVERTICALBLANKEVENT2
 - D3DKMT_WAITFORVERTICALBLANKEVENT2
 - d3dkmthk/D3DKMT_WAITFORVERTICALBLANKEVENT2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - D3DKMT_WAITFORVERTICALBLANKEVENT2
---

# _D3DKMT_WAITFORVERTICALBLANKEVENT2 structure


## -description

Describes parameters for multiple wait objects, including a vertical blank event. Supported starting with Windows 8.

## -struct-fields

### -field hAdapter

[in] A handle to the adapter.

### -field hDevice

[in] A handle to the display device. This member is optionally specified. However, if the OpenGL ICD specifies the display device, the kernel is given more optimization opportunities with regard to power usage.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the VidPN source.

### -field NumObjects

The number of wait objects to wait on, which equals the size of the array specified by the <b>ObjectHandleArray</b> member.

### -field ObjectHandleArray

[in] A handle to an array of wait objects to wait on.

