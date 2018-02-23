---
UID: NE:d3dkmdt._D3DKMDT_MODE_PREFERENCE
title: "_D3DKMDT_MODE_PREFERENCE"
author: windows-driver-content
description: The D3DKMDT_MODE_PREFERENCE enumeration is used to indicate whether a particular mode is one of the modes preferred by the monitor connected to a given video present target.
old-location: display\d3dkmdt_mode_preference.htm
old-project: display
ms.assetid: 5d18431d-ca35-4757-8bbe-9397abd31568
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DKMDT_MP_UNINITIALIZED, d3dkmdt/D3DKMDT_MP_PREFERRED, D3DKMDT_MP_NOTPREFERRED, display.d3dkmdt_mode_preference, D3DKMDT_MODE_PREFERENCE enumeration [Display Devices], D3DKMDT_MODE_PREFERENCE, d3dkmdt/D3DKMDT_MP_NOTPREFERRED, _D3DKMDT_MODE_PREFERENCE, D3DKMDT_MP_PREFERRED, DmEnums_b5bdbc2e-4abe-4db7-8700-e34fc0125472.xml, d3dkmdt/D3DKMDT_MP_UNINITIALIZED, d3dkmdt/D3DKMDT_MODE_PREFERENCE
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_MODE_PREFERENCE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MODE_PREFERENCE
---

# _D3DKMDT_MODE_PREFERENCE enumeration


## -description


The D3DKMDT_MODE_PREFERENCE enumeration is used to indicate whether a particular mode is one of the modes preferred by the monitor connected to a given video present target.


## -syntax


````
typedef enum _D3DKMDT_MODE_PREFERENCE { 
  D3DKMDT_MP_UNINITIALIZED  = 0,
  D3DKMDT_MP_PREFERRED      = 1,
  D3DKMDT_MP_NOTPREFERRED   = 2
} D3DKMDT_MODE_PREFERENCE;
````


## -enum-fields




### -field D3DKMDT_MP_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MODE_PREFERENCE has not yet been assigned a meaningful value.


### -field D3DKMDT_MP_PREFERRED

Indicates that the mode is preferred by the monitor.


### -field D3DKMDT_MP_NOTPREFERRED

Indicates that the mode is not preferred by the monitor.


## -remarks



The <b>Info</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a> structure and the <b>SignalInfo</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure are <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_signal_info.md">D3DKMDT_VIDEO_SIGNAL_MODE</a> structures. The <b>ModePreference</b> member of the D3DKMDT_VIDEO_SIGNAL_MODE structure is a D3DKMDT_MODE_PREFERENCE value.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_MODE_PREFERENCE enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

