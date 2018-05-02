---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
title: "_D3DKMDT_MONITOR_CAPABILITIES_ORIGIN"
author: windows-driver-content
description: The D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration is used to indicate where a monitor's capability information was obtained.
old-location: display\d3dkmdt_monitor_capabilities_origin.htm
old-project: display
ms.assetid: fbbea7d7-2bd7-4dd0-bcb8-3fc93c7474a3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMDT_MCO_DEFAULTMONITORPROFILE, D3DKMDT_MCO_DRIVER, D3DKMDT_MCO_MONITORDESCRIPTOR, D3DKMDT_MCO_MONITORDESCRIPTOR_REGISTRYOVERRIDE, D3DKMDT_MCO_SPECIFICCAP_REGISTRYOVERRIDE, D3DKMDT_MCO_UNINITIALIZED, D3DKMDT_MONITOR_CAPABILITIES_ORIGIN, D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration [Display Devices], DmEnums_fc03a227-b0c7-4152-a4f0-c8badee981e5.xml, _D3DKMDT_MONITOR_CAPABILITIES_ORIGIN, d3dkmdt/D3DKMDT_MCO_DEFAULTMONITORPROFILE, d3dkmdt/D3DKMDT_MCO_DRIVER, d3dkmdt/D3DKMDT_MCO_MONITORDESCRIPTOR, d3dkmdt/D3DKMDT_MCO_MONITORDESCRIPTOR_REGISTRYOVERRIDE, d3dkmdt/D3DKMDT_MCO_SPECIFICCAP_REGISTRYOVERRIDE, d3dkmdt/D3DKMDT_MCO_UNINITIALIZED, d3dkmdt/D3DKMDT_MONITOR_CAPABILITIES_ORIGIN, display.d3dkmdt_monitor_capabilities_origin
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
-	D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
---

# _D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration


## -description


The D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration is used to indicate where a monitor's capability information was obtained.


## -enum-fields




### -field D3DKMDT_MCO_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_CAPABILITIES_ORIGIN has not yet been assigned a meaningful value.


### -field D3DKMDT_MCO_DEFAULTMONITORPROFILE

Indicates that the capability information was obtained from the default monitor profile.


### -field D3DKMDT_MCO_MONITORDESCRIPTOR

Indicates that the capability information was obtained from an Extended Display Information Data (EDID) descriptor.


### -field D3DKMDT_MCO_MONITORDESCRIPTOR_REGISTRYOVERRIDE

Indicates that the capability information was obtained from an INF file section that overrides the monitor's EDID descriptor.


### -field D3DKMDT_MCO_SPECIFICCAP_REGISTRYOVERRIDE

Indicates that the capability information was obtained from an INF file section that overrides a single capability.


### -field D3DKMDT_MCO_DRIVER

Indicates that the capability information was obtained by a call to the display miniport driver's <a href="https://msdn.microsoft.com/1fa29ab6-1faa-4be6-ae87-4cac9057471d">DxgkDdiRecommendMonitorModes</a> function.


## -remarks



The <b>Origin</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure is a constant from the D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568435">Monitor Source Mode Set Interface</a>
 

 

