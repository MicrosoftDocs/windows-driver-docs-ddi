---
UID: NS:d3dkmthk._D3DKMT_INVALIDATEACTIVEVIDPN
title: _D3DKMT_INVALIDATEACTIVEVIDPN (d3dkmthk.h)
description: The D3DKMT_INVALIDATEACTIVEVIDPN structure describes parameters that invalidate the active video present network (VidPN) currently in use.
old-location: display\d3dkmt_invalidateactivevidpn.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_INVALIDATEACTIVEVIDPN structure"]
ms.keywords: D3DKMT_INVALIDATEACTIVEVIDPN, D3DKMT_INVALIDATEACTIVEVIDPN structure [Display Devices], OpenGL_Structs_6610529b-39db-4fc4-981a-96a6b3bf7543.xml, _D3DKMT_INVALIDATEACTIVEVIDPN, d3dkmthk/D3DKMT_INVALIDATEACTIVEVIDPN, display.d3dkmt_invalidateactivevidpn
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
req.typenames: D3DKMT_INVALIDATEACTIVEVIDPN
f1_keywords:
 - _D3DKMT_INVALIDATEACTIVEVIDPN
 - d3dkmthk/_D3DKMT_INVALIDATEACTIVEVIDPN
 - D3DKMT_INVALIDATEACTIVEVIDPN
 - d3dkmthk/D3DKMT_INVALIDATEACTIVEVIDPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_INVALIDATEACTIVEVIDPN
---

# _D3DKMT_INVALIDATEACTIVEVIDPN structure


## -description

The D3DKMT_INVALIDATEACTIVEVIDPN structure describes parameters that invalidate the active video present network (VidPN) currently in use.

## -struct-fields

### -field hAdapter

[in] A handle to the graphics adapter that the VidPN exists on.

### -field pPrivateDriverData

[in] A pointer to a buffer that contains the display mode (for example, clone-view mode) that the OpenGL installable client driver (ICD) requests for the new VidPN.

### -field PrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtinvalidateactivevidpn">D3DKMTInvalidateActiveVidPn</a>
