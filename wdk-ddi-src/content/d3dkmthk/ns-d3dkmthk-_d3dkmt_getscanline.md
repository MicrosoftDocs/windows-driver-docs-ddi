---
UID: NS:d3dkmthk._D3DKMT_GETSCANLINE
title: _D3DKMT_GETSCANLINE (d3dkmthk.h)
description: The D3DKMT_GETSCANLINE structure contains information about a video present source's vertical blanking status.
old-location: display\d3dkmt_getscanline.htm
ms.assetid: af06c31e-0c4f-4e2a-8d19-84c1c63d6bd0
ms.date: 05/10/2018
keywords: ["D3DKMT_GETSCANLINE structure"]
ms.keywords: D3DKMT_GETSCANLINE, D3DKMT_GETSCANLINE structure [Display Devices], OpenGL_Structs_1e99e2c0-2215-43ed-9dc4-657f30903637.xml, _D3DKMT_GETSCANLINE, d3dkmthk/D3DKMT_GETSCANLINE, display.d3dkmt_getscanline
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
req.typenames: D3DKMT_GETSCANLINE
f1_keywords:
 - _D3DKMT_GETSCANLINE
 - d3dkmthk/_D3DKMT_GETSCANLINE
 - D3DKMT_GETSCANLINE
 - d3dkmthk/D3DKMT_GETSCANLINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_GETSCANLINE
---

# _D3DKMT_GETSCANLINE structure


## -description

The D3DKMT_GETSCANLINE structure contains information about a video present source's vertical blanking status.

## -struct-fields

### -field hAdapter

[in] A handle to a graphics adapter.

### -field VidPnSourceId

[in] The identifier of a graphics adapter's video present source.

### -field InVerticalBlank

[out] A Boolean variable that receives <b>TRUE</b> if the video present source is in vertical blanking mode and <b>FALSE</b> if the video present source is not in vertical blanking mode.

### -field ScanLine

[out] The video present source's current scan line.

## -remarks

A video present path represents a connection between a video present source (view) and a video present target (output) on a graphics adapter. For more information about video present networks, paths, sources, and targets, see <a href="/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetscanline">D3DKMTGetScanLine</a>