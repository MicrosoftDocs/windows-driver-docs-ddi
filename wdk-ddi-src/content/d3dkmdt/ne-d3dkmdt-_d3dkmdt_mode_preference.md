---
UID: NE:d3dkmdt._D3DKMDT_MODE_PREFERENCE
title: _D3DKMDT_MODE_PREFERENCE (d3dkmdt.h)
description: The D3DKMDT_MODE_PREFERENCE enumeration is used to indicate whether a particular mode is one of the modes preferred by the monitor connected to a given video present target.
old-location: display\d3dkmdt_mode_preference.htm
tech.root: display
ms.assetid: 5d18431d-ca35-4757-8bbe-9397abd31568
ms.date: 05/10/2018
ms.keywords: D3DKMDT_MODE_PREFERENCE, D3DKMDT_MODE_PREFERENCE enumeration [Display Devices], D3DKMDT_MP_NOTPREFERRED, D3DKMDT_MP_PREFERRED, D3DKMDT_MP_UNINITIALIZED, DmEnums_b5bdbc2e-4abe-4db7-8700-e34fc0125472.xml, _D3DKMDT_MODE_PREFERENCE, d3dkmdt/D3DKMDT_MODE_PREFERENCE, d3dkmdt/D3DKMDT_MP_NOTPREFERRED, d3dkmdt/D3DKMDT_MP_PREFERRED, d3dkmdt/D3DKMDT_MP_UNINITIALIZED, display.d3dkmdt_mode_preference
f1_keywords:
 - "d3dkmdt/D3DKMDT_MODE_PREFERENCE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- D3DKMDT_MODE_PREFERENCE
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_MODE_PREFERENCE
---

# _D3DKMDT_MODE_PREFERENCE enumeration


## -description


The D3DKMDT_MODE_PREFERENCE enumeration is used to indicate whether a particular mode is one of the modes preferred by the monitor connected to a given video present target.


## -enum-fields




### -field D3DKMDT_MP_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MODE_PREFERENCE has not yet been assigned a meaningful value.


### -field D3DKMDT_MP_PREFERRED

Indicates that the mode is preferred by the monitor.


### -field D3DKMDT_MP_NOTPREFERRED

Indicates that the mode is not preferred by the monitor.


## -remarks



The <b>Info</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure and the <b>SignalInfo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure are <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_signal_info">D3DKMDT_VIDEO_SIGNAL_MODE</a> structures. The <b>ModePreference</b> member of the D3DKMDT_VIDEO_SIGNAL_MODE structure is a D3DKMDT_MODE_PREFERENCE value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>
 

 

