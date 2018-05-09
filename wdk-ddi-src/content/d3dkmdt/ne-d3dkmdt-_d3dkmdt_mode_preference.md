---
UID: NE:d3dkmdt._D3DKMDT_MODE_PREFERENCE
title: "_D3DKMDT_MODE_PREFERENCE"
author: windows-driver-content
description: The D3DKMDT_MODE_PREFERENCE enumeration is used to indicate whether a particular mode is one of the modes preferred by the monitor connected to a given video present target.
old-location: display\d3dkmdt_mode_preference.htm
old-project: display
ms.assetid: 5d18431d-ca35-4757-8bbe-9397abd31568
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMDT_MODE_PREFERENCE, D3DKMDT_MODE_PREFERENCE enumeration [Display Devices], D3DKMDT_MP_NOTPREFERRED, D3DKMDT_MP_PREFERRED, D3DKMDT_MP_UNINITIALIZED, DmEnums_b5bdbc2e-4abe-4db7-8700-e34fc0125472.xml, _D3DKMDT_MODE_PREFERENCE, d3dkmdt/D3DKMDT_MODE_PREFERENCE, d3dkmdt/D3DKMDT_MP_NOTPREFERRED, d3dkmdt/D3DKMDT_MP_PREFERRED, d3dkmdt/D3DKMDT_MP_UNINITIALIZED, display.d3dkmdt_mode_preference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_MODE_PREFERENCE
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



The <b>Info</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure and the <b>SignalInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure are <a href="https://msdn.microsoft.com/38d0a655-265b-46e0-8af3-de6757025588">D3DKMDT_VIDEO_SIGNAL_MODE</a> structures. The <b>ModePreference</b> member of the D3DKMDT_VIDEO_SIGNAL_MODE structure is a D3DKMDT_MODE_PREFERENCE value.




## -see-also




<a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>
 

 

