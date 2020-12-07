---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_ORIENTATION
title: _D3DKMDT_MONITOR_ORIENTATION (d3dkmdt.h)
description: The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device.
old-location: display\d3dkmdt_monitor_orientation.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DKMDT_MONITOR_ORIENTATION enumeration"]
ms.keywords: D3DKMDT_MONITOR_ORIENTATION, D3DKMDT_MONITOR_ORIENTATION enumeration [Display Devices], D3DKMDT_MO_0DEG, D3DKMDT_MO_180DEG, D3DKMDT_MO_270DEG, D3DKMDT_MO_90DEG, D3DKMDT_MO_UNINITIALIZED, DmEnums_d8dfc33b-5b13-4fb0-8ef4-091c5b018424.xml, _D3DKMDT_MONITOR_ORIENTATION, d3dkmdt/D3DKMDT_MONITOR_ORIENTATION, d3dkmdt/D3DKMDT_MO_0DEG, d3dkmdt/D3DKMDT_MO_180DEG, d3dkmdt/D3DKMDT_MO_270DEG, d3dkmdt/D3DKMDT_MO_90DEG, d3dkmdt/D3DKMDT_MO_UNINITIALIZED, display.d3dkmdt_monitor_orientation
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
req.typenames: D3DKMDT_MONITOR_ORIENTATION
f1_keywords:
 - _D3DKMDT_MONITOR_ORIENTATION
 - d3dkmdt/_D3DKMDT_MONITOR_ORIENTATION
 - D3DKMDT_MONITOR_ORIENTATION
 - d3dkmdt/D3DKMDT_MONITOR_ORIENTATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - D3DKMDT_MONITOR_ORIENTATION
---

# _D3DKMDT_MONITOR_ORIENTATION enumeration


## -description

The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device.

## -enum-fields

### -field D3DKMDT_MO_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_ORIENTATION has not yet been assigned a meaningful value.

### -field D3DKMDT_MO_0DEG

Indicates that the display device has not been rotated from its default orientation.

### -field D3DKMDT_MO_90DEG

Indicates that the display device has been rotated 90 degrees clockwise from its default orientation.

### -field D3DKMDT_MO_180DEG

Indicates that the display device has been rotated 180 degrees clockwise from its default orientation.

### -field D3DKMDT_MO_270DEG

Indicates that the display device has been rotated 270 degrees clockwise from its default orientation.

