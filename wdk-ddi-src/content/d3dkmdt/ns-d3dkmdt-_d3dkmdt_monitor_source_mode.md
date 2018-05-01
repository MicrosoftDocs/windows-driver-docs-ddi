---
UID: NS:d3dkmdt._D3DKMDT_MONITOR_SOURCE_MODE
title: "_D3DKMDT_MONITOR_SOURCE_MODE"
author: windows-driver-content
description: The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode.
old-location: display\d3dkmdt_monitor_source_mode.htm
old-project: display
ms.assetid: bccacf88-b66b-4d55-b3a8-9d9b8cfcede8
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMDT_MONITOR_SOURCE_MODE, D3DKMDT_MONITOR_SOURCE_MODE structure [Display Devices], DmStructs_165795ef-f70e-4f50-a35f-c6009c547be2.xml, _D3DKMDT_MONITOR_SOURCE_MODE, d3dkmdt/D3DKMDT_MONITOR_SOURCE_MODE, display.d3dkmdt_monitor_source_mode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3DKMDT_MONITOR_SOURCE_MODE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_SOURCE_MODE
---

# _D3DKMDT_MONITOR_SOURCE_MODE structure


## -description


The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode.


## -struct-fields




### -field Id

An integer that identifies the monitor source mode.


### -field VideoSignalInfo

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546625">D3DKMDT_VIDEO_SIGNAL_INFO</a> enumerator that indicates the video mode standard (if any) that defines the mode.


### -field ColorBasis

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff545984">D3DKMDT_COLOR_BASIS</a> enumerator that indicates the color basis of the mode.


### -field ColorCoeffDynamicRanges

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff545986">D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES</a> structure that contains the dynamic ranges for the color channels in the mode's color basis.


### -field Origin

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546075">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> enumeration that indicates the source of the mode information. For example the mode information could be from a default monitor profile or it could be from an override in an INF file.


### -field Preference

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546061">D3DKMDT_MODE_PREFERENCE</a> enumeration that indicates whether the mode is the preferred mode in a <a href="https://msdn.microsoft.com/d2ff3c18-4b4d-41c1-aba1-a50daaf18602">monitor source mode set</a>.


## -remarks



The D3DKMDT_MONITOR_SOURCE_MODE_ID data type is defined in <i>D3dkmdt.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a>
 

 

