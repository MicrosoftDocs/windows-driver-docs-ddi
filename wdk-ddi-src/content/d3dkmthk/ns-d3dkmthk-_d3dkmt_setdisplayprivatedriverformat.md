---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
title: _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT (d3dkmthk.h)
description: The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source.
old-location: display\d3dkmt_setdisplayprivatedriverformat.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure"]
ms.keywords: D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure [Display Devices], OpenGL_Structs_c5440fbe-47f2-43eb-ae09-e9295bfa4bad.xml, _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, d3dkmthk/D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, display.d3dkmt_setdisplayprivatedriverformat
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
req.typenames: D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
f1_keywords:
 - _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
 - d3dkmthk/_D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
 - D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
 - d3dkmthk/D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
 - D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
---

# _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure


## -description

The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source.

## -struct-fields

### -field hDevice

[in] A handle to the device that requests to change the private-format attribute of a video present source.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to set a private-format attribute on (that is, the identifier of the primary surface to set a private-format attribute on).

### -field PrivateDriverFormatAttribute

[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplayprivatedriverformat">D3DKMTSetDisplayPrivateDriverFormat</a>

