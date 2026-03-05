---
UID: NE:iddcx.IDDCX_MONITOR_DESCRIPTION_TYPE
title: IDDCX_MONITOR_DESCRIPTION_TYPE (iddcx.h)
description: Used to describe the monitor description.
prerelease: true
old-location: display\iddcx_monitor_description_type.htm
tech.root: display
ms.date: 02/17/2026
keywords: ["IDDCX_MONITOR_DESCRIPTION_TYPE enumeration"]
ms.keywords: IDDCX_MONITOR_DESCRIPTION_TYPE, IDDCX_MONITOR_DESCRIPTION_TYPE enumeration [Display Devices], IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, IDDCX_MONITOR_DESCRIPTION_TYPE_EDID, IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED, display.iddcx_monitor_description_type, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_EDID, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
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
req.typenames: 
f1_keywords:
 - IDDCX_MONITOR_DESCRIPTION_TYPE
 - iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_MONITOR_DESCRIPTION_TYPE
---

# IDDCX_MONITOR_DESCRIPTION_TYPE enumeration

## -description

An **IDDCX_MONITOR_DESCRIPTION_TYPE** value describes the monitor type.

## -enum-fields

### -field IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED:0

Indicates that an **IDDCX_MONITOR_DESCRIPTION_TYPE** variable has not yet been assigned a meaningful value.

### -field IDDCX_MONITOR_DESCRIPTION_TYPE_EDID:1

The monitor description is either EDID or no monitor description is available.

### -field IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID_AND_EDID:2

The monitor description is both DisplayID and EDID.

### -field IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID: 3

The monitor description is DisplayID only. This means a pure DisplayID block, rather than one embedded inside an EDID block, and no EDID blocks preceding or following.

## -see-also

[**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md)
