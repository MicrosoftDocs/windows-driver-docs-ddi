---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMHDC
title: _D3DKMT_OPENADAPTERFROMHDC (d3dkmthk.h)
description: The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromhdc.htm
ms.assetid: db425b8c-4abd-4998-89bb-f6d9f066a3f6
ms.date: 05/10/2018
keywords: ["D3DKMT_OPENADAPTERFROMHDC structure"]
ms.keywords: D3DKMT_OPENADAPTERFROMHDC, D3DKMT_OPENADAPTERFROMHDC structure [Display Devices], OpenGL_Structs_a4c2aa1b-b17c-4e81-a0d2-9776cec61112.xml, _D3DKMT_OPENADAPTERFROMHDC, d3dkmthk/D3DKMT_OPENADAPTERFROMHDC, display.d3dkmt_openadapterfromhdc
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
req.typenames: D3DKMT_OPENADAPTERFROMHDC
f1_keywords:
 - _D3DKMT_OPENADAPTERFROMHDC
 - d3dkmthk/_D3DKMT_OPENADAPTERFROMHDC
 - D3DKMT_OPENADAPTERFROMHDC
 - d3dkmthk/D3DKMT_OPENADAPTERFROMHDC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_OPENADAPTERFROMHDC
---

# _D3DKMT_OPENADAPTERFROMHDC structure


## -description

The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output.

## -struct-fields

### -field hDc

[in] The HDC for the graphics adapter and monitor output that are retrieved.

### -field hAdapter

[out] A handle to the graphics adapter for the HDC that <b>hDc</b> specifies. The adapter handle is returned from the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenadapterfromhdc">D3DKMTOpenAdapterFromHdc</a> function.

### -field AdapterLuid

[out] The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) of the graphics adapter for the HDC that <b>hDc</b> specifies. The LUID is returned from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenadapterfromhdc">D3DKMTOpenAdapterFromHdc</a> call.

### -field VidPnSourceId

[out] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the HDC that <b>hDc</b> specifies. The identification number is returned from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenadapterfromhdc">D3DKMTOpenAdapterFromHdc</a> call.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenadapterfromhdc">D3DKMTOpenAdapterFromHdc</a>

