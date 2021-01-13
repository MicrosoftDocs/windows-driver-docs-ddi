---
UID: NS:d3dkmdt._D3DKMDT_VIDEO_PRESENT_TARGET
title: _D3DKMDT_VIDEO_PRESENT_TARGET (d3dkmdt.h)
description: The D3DKMDT_VIDEO_PRESENT_TARGET structure contains information about a video present target.
old-location: display\d3dkmdt_video_present_target.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_VIDEO_PRESENT_TARGET structure"]
ms.keywords: D3DKMDT_VIDEO_PRESENT_TARGET, D3DKMDT_VIDEO_PRESENT_TARGET structure [Display Devices], DmStructs_ef451c58-7ee5-4c52-9afe-9aab45114186.xml, _D3DKMDT_VIDEO_PRESENT_TARGET, d3dkmdt/D3DKMDT_VIDEO_PRESENT_TARGET, display.d3dkmdt_video_present_target
req.header: d3dkmdt.h
req.include-header:
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
req.typenames: D3DKMDT_VIDEO_PRESENT_TARGET
f1_keywords:
 - _D3DKMDT_VIDEO_PRESENT_TARGET
 - d3dkmdt/_D3DKMDT_VIDEO_PRESENT_TARGET
 - D3DKMDT_VIDEO_PRESENT_TARGET
 - d3dkmdt/D3DKMDT_VIDEO_PRESENT_TARGET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_VIDEO_PRESENT_TARGET
---

# _D3DKMDT_VIDEO_PRESENT_TARGET structure


## -description

The D3DKMDT_VIDEO_PRESENT_TARGET structure contains information about a video present target.

## -struct-fields

### -field Id

An integer that uniquely identifies the video present target.

### -field VideoOutputTechnology

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_video_output_technology">D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY</a> enumerator that indicates the target's output technology (for example HD15, DVI, HDMI).

### -field VideoOutputHpdAwareness

A value from the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgk_child_device_hpd_awareness">DXGK_CHILD_DEVICE_HPD_AWARENESS</a> enumeration that indicates the target's ability to detect that a monitor has been hot plugged or unplugged.

### -field MonitorOrientationAwareness

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_orientation_awareness">D3DKMDT_MONITOR_ORIENTATION_AWARENESS</a> enumerator that indicates the target's ability to detect that a connected monitor (or other display device) has been rotated.

### -field SupportsSdtvModes

Indicates whether the video output supports standard definition TV (SDTV) modes.

## -remarks

The D3DDDI_VIDEO_PRESENT_TARGET_ID data type is defined in <i>D3dukmdt.h</i>.

Video present target identifiers are assigned by the display miniport driver. <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

For more information about video present targets, see <a href="/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_source">D3DKMDT_VIDEO_PRESENT_SOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>
