---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_TARGET_MODE
title: D3DKMDT_VIDPN_TARGET_MODE (d3dkmdt.h)
description: The D3DKMDT_VIDPN_TARGET_MODE structure contains information about a video present network (VidPN) target mode.
old-location: display\d3dkmdt_vidpn_target_mode.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_VIDPN_TARGET_MODE structure"]
ms.keywords: D3DKMDT_VIDPN_TARGET_MODE, D3DKMDT_VIDPN_TARGET_MODE structure [Display Devices], DmStructs_a1ac1f39-cd89-458b-95b5-91fd5cbc507e.xml, _D3DKMDT_VIDPN_TARGET_MODE, d3dkmdt/D3DKMDT_VIDPN_TARGET_MODE, display.d3dkmdt_vidpn_target_mode
req.header: d3dkmdt.h
req.include-header: 
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
req.typenames: D3DKMDT_VIDPN_TARGET_MODE
f1_keywords:
 - _D3DKMDT_VIDPN_TARGET_MODE
 - d3dkmdt/_D3DKMDT_VIDPN_TARGET_MODE
 - D3DKMDT_VIDPN_TARGET_MODE
 - d3dkmdt/D3DKMDT_VIDPN_TARGET_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMDT_VIDPN_TARGET_MODE
 - D3DKMDT_VIDPN_TARGET_MODE
---

# D3DKMDT_VIDPN_TARGET_MODE structure

## -description

The **D3DKMDT_VIDPN_TARGET_MODE** structure contains information about a video present network (VidPN) target mode.

## -struct-fields

### -field Id

An integer that identifies the target mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see [**pfnCreateNewModeInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md).

### -field VideoSignalInfo

A [**D3DKMDT_VIDEO_SIGNAL_INFO**](ns-d3dkmdt-_d3dkmdt_video_signal_info.md) structure that contains information about the target mode (for example, video standard, resolution, refresh rate).

### -field WireFormatAndPreference

A [**D3DKMDT_WIRE_FORMAT_AND_PREFERENCE**](ns-d3dkmdt-_d3dkmdt_wire_format_and_preference.md) structure that specifies the wire format and preference.

### -field Preference

A [**D3DKMDT_MODE_PREFERENCE**](ne-d3dkmdt-_d3dkmdt_mode_preference.md) enumerator that indicates whether a particular mode is one of the modes that is preferred by the monitor that is connected to the video present target.

### -field MinimumVSyncFreq

The minimum vertical sync frequency of the monitor. Available starting in Windows Server 2022 (WDDM 2.9).

## -remarks

For more information about video present targets and VidPN target modes, see [Introduction to Video Present Networks](/windows-hardware/drivers/display/introduction-to-video-present-networks) and [Enumerating Cofunctional VidPN Source and Target Modes](/windows-hardware/drivers/display/enumerating-cofunctional-vidpn-source-and-target-modes).

## -see-also

[**D3DKMDT_MONITOR_SOURCE_MODE**](ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md)

[**D3DKMDT_VIDPN_SOURCE_MODE**](ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md)
