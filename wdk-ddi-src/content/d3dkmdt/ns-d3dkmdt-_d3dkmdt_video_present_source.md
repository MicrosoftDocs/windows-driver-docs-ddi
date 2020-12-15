---
UID: NS:d3dkmdt._D3DKMDT_VIDEO_PRESENT_SOURCE
title: _D3DKMDT_VIDEO_PRESENT_SOURCE (d3dkmdt.h)
description: The D3DKMDT_VIDEO_PRESENT_SOURCE structure contains the unique identifier of a video present source.
old-location: display\d3dkmdt_video_present_source.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_VIDEO_PRESENT_SOURCE structure"]
ms.keywords: D3DKMDT_VIDEO_PRESENT_SOURCE, D3DKMDT_VIDEO_PRESENT_SOURCE structure [Display Devices], DmStructs_16a61d68-9479-420e-b936-a1a0506ce8c3.xml, _D3DKMDT_VIDEO_PRESENT_SOURCE, d3dkmdt/D3DKMDT_VIDEO_PRESENT_SOURCE, display.d3dkmdt_video_present_source
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.typenames: D3DKMDT_VIDEO_PRESENT_SOURCE
f1_keywords:
 - _D3DKMDT_VIDEO_PRESENT_SOURCE
 - d3dkmdt/_D3DKMDT_VIDEO_PRESENT_SOURCE
 - D3DKMDT_VIDEO_PRESENT_SOURCE
 - d3dkmdt/D3DKMDT_VIDEO_PRESENT_SOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_VIDEO_PRESENT_SOURCE
---

# _D3DKMDT_VIDEO_PRESENT_SOURCE structure


## -description

The D3DKMDT_VIDEO_PRESENT_SOURCE structure contains the unique identifier of a video present source.

## -struct-fields

### -field Id

The identifier of a video present source.

### -field dwReserved

Reserved for future use.

## -remarks

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

Video present source identifiers are assigned by the operating system. <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... NÂ -Â 1.

For more information about video present sources, see <a href="/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_target">D3DKMDT_VIDEO_PRESENT_TARGET</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>
