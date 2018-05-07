---
UID: NS:d3dkmdt._D3DKMDT_MONITOR_FREQUENCY_RANGE
title: "_D3DKMDT_MONITOR_FREQUENCY_RANGE"
author: windows-driver-content
description: The D3DKMDT_MONITOR_FREQUENCY_RANGE structure contains information about a range of frequencies supported by a monitor.
old-location: display\d3dkmdt_monitor_frequency_range.htm
old-project: display
ms.assetid: 241b0534-593a-4030-9c48-8d463d56b64a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMDT_MONITOR_FREQUENCY_RANGE, D3DKMDT_MONITOR_FREQUENCY_RANGE structure [Display Devices], DmStructs_ba8a984e-da56-4f63-a0b8-d94d426df563.xml, _D3DKMDT_MONITOR_FREQUENCY_RANGE, d3dkmdt/D3DKMDT_MONITOR_FREQUENCY_RANGE, display.d3dkmdt_monitor_frequency_range
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
-	D3DKMDT_MONITOR_FREQUENCY_RANGE
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_FREQUENCY_RANGE
---

# _D3DKMDT_MONITOR_FREQUENCY_RANGE structure


## -description


The D3DKMDT_MONITOR_FREQUENCY_RANGE structure contains information about a range of frequencies supported by a monitor.


## -struct-fields




### -field Origin

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546075">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> enumeration that indicates the source of the frequency range information.


### -field RangeLimits

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546008">D3DKMDT_FREQUENCY_RANGE</a> structure that contains the minimum and maximum refresh rates supported by the monitor.


### -field ConstraintType

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546109">D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT</a> enumeration that specifies the type of constraint under which the frequency range is supported.


### -field Constraint

A union that contains either the active region size or the maximum pixel rate in the following members.


### -field Constraint.ActiveSize

If <b>ConstraintType</b> is equal to D3DKMDT_MFRC_ACTIVESIZE, then this member specifies the maximum active region size for which the frequency range is supported.


### -field Constraint.MaxPixelRate

If <b>ConstraintType</b> is equal to D3DKMDT_MFRC_MAXPIXELRATE, then this member specifies the maximum pixel rate for which the frequency range is supported.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568430">Monitor Frequency Range Set Interface</a>
 

 

