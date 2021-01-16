---
UID: NS:d3dkmdt._D3DKMDT_MONITOR_FREQUENCY_RANGE
title: _D3DKMDT_MONITOR_FREQUENCY_RANGE (d3dkmdt.h)
description: The D3DKMDT_MONITOR_FREQUENCY_RANGE structure contains information about a range of frequencies supported by a monitor.
old-location: display\d3dkmdt_monitor_frequency_range.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_MONITOR_FREQUENCY_RANGE structure"]
ms.keywords: D3DKMDT_MONITOR_FREQUENCY_RANGE, D3DKMDT_MONITOR_FREQUENCY_RANGE structure [Display Devices], DmStructs_ba8a984e-da56-4f63-a0b8-d94d426df563.xml, _D3DKMDT_MONITOR_FREQUENCY_RANGE, d3dkmdt/D3DKMDT_MONITOR_FREQUENCY_RANGE, display.d3dkmdt_monitor_frequency_range
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
req.typenames: D3DKMDT_MONITOR_FREQUENCY_RANGE
f1_keywords:
 - _D3DKMDT_MONITOR_FREQUENCY_RANGE
 - d3dkmdt/_D3DKMDT_MONITOR_FREQUENCY_RANGE
 - D3DKMDT_MONITOR_FREQUENCY_RANGE
 - d3dkmdt/D3DKMDT_MONITOR_FREQUENCY_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMDT_MONITOR_FREQUENCY_RANGE
 - D3DKMDT_MONITOR_FREQUENCY_RANGE
product:
 - Windows
---

# _D3DKMDT_MONITOR_FREQUENCY_RANGE structure


## -description

The D3DKMDT_MONITOR_FREQUENCY_RANGE structure contains information about a range of frequencies supported by a monitor.

## -struct-fields

### -field Origin

A value from the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> enumeration that indicates the source of the frequency range information.

### -field RangeLimits

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_frequency_range">D3DKMDT_FREQUENCY_RANGE</a> structure that contains the minimum and maximum refresh rates supported by the monitor.

### -field ConstraintType

A value from the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_frequency_range_constraint">D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT</a> enumeration that specifies the type of constraint under which the frequency range is supported.

### -field Constraint

A union that contains either the active region size or the maximum pixel rate in the following members.

### -field ActiveSize

If <b>ConstraintType</b> is equal to D3DKMDT_MFRC_ACTIVESIZE, then this member specifies the maximum active region size for which the frequency range is supported.

### -field MaxPixelRate

If <b>ConstraintType</b> is equal to D3DKMDT_MFRC_MAXPIXELRATE, then this member specifies the maximum pixel rate for which the frequency range is supported.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">Monitor Frequency Range Set Interface</a>

