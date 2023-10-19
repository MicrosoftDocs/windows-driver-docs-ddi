---
UID: NS:d3dkmthk._D3DKMT_GETDISPLAYMODELIST
title: D3DKMT_GETDISPLAYMODELIST (d3dkmthk.h)
description: Learn more about the D3DKMT_GETDISPLAYMODELIST structure.
ms.date: 10/19/2023
keywords: ["D3DKMT_GETDISPLAYMODELIST structure"]
ms.keywords: D3DKMT_GETDISPLAYMODELIST, D3DKMT_GETDISPLAYMODELIST structure [Display Devices], OpenGL_Structs_27c1c3f3-6316-4dc3-b83d-1a8f6f6360bb.xml, _D3DKMT_GETDISPLAYMODELIST, d3dkmthk/D3DKMT_GETDISPLAYMODELIST, display.d3dkmt_getdisplaymodelist
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DKMT_GETDISPLAYMODELIST
f1_keywords:
 - _D3DKMT_GETDISPLAYMODELIST
 - d3dkmthk/_D3DKMT_GETDISPLAYMODELIST
 - D3DKMT_GETDISPLAYMODELIST
 - d3dkmthk/D3DKMT_GETDISPLAYMODELIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_GETDISPLAYMODELIST
 - D3DKMT_GETDISPLAYMODELIST
---

# D3DKMT_GETDISPLAYMODELIST structure

## -description

The **D3DKMT_GETDISPLAYMODELIST** structure describes a list of display modes.

## -struct-fields

### -field hAdapter

[in] A handle to the graphics adapter.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display modes apply to.

### -field pModeList

[in/out] An array of [**D3DKMT_DISPLAYMODE**](ns-d3dkmthk-_d3dkmt_displaymode.md) structures that represent the list of display modes. If **pModeList** is NULL and **ModeCount** is zero on input, [**D3DKMTGetDisplayModeList**](nf-d3dkmthk-d3dkmtgetdisplaymodelist.md) sets **ModeCount** to be the number of display modes for the specified **VidPnSourceId** on the specified graphics adapter.

### -field ModeCount

[in/out] The number of display modes in the array that **pModeList** specifies. If **pModeList** is NULL and **ModeCount** is zero on input, [**D3DKMTGetDisplayModeList**](nf-d3dkmthk-d3dkmtgetdisplaymodelist.md) sets **ModeCount** to be the number of display modes for the specified **VidPnSourceId** on the specified graphics adapter.

## -see-also

[**D3DKMTGetDisplayModeList**](nf-d3dkmthk-d3dkmtgetdisplaymodelist.md)

[**D3DKMT_DISPLAYMODE**](ns-d3dkmthk-_d3dkmt_displaymode.md)
