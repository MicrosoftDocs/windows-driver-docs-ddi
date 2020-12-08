---
UID: NS:d3dkmddi._DXGKARG_SETTARGETANALOGCOPYPROTECTION
title: _DXGKARG_SETTARGETANALOGCOPYPROTECTION (d3dkmddi.h)
description: Holds information to set analog copy protection on a display adapter's video present target.
old-location: display\dxgkarg_settargetanalogcopyprotection.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_SETTARGETANALOGCOPYPROTECTION structure"]
ms.keywords: DXGKARG_SETTARGETANALOGCOPYPROTECTION, DXGKARG_SETTARGETANALOGCOPYPROTECTION structure [Display Devices], _DXGKARG_SETTARGETANALOGCOPYPROTECTION, d3dkmddi/DXGKARG_SETTARGETANALOGCOPYPROTECTION, display.dxgkarg_settargetanalogcopyprotection
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
tech.root: display
req.typenames: DXGKARG_SETTARGETANALOGCOPYPROTECTION
f1_keywords:
 - _DXGKARG_SETTARGETANALOGCOPYPROTECTION
 - d3dkmddi/_DXGKARG_SETTARGETANALOGCOPYPROTECTION
 - DXGKARG_SETTARGETANALOGCOPYPROTECTION
 - d3dkmddi/DXGKARG_SETTARGETANALOGCOPYPROTECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_SETTARGETANALOGCOPYPROTECTION
---

# _DXGKARG_SETTARGETANALOGCOPYPROTECTION structure


## -description

Holds information to set analog copy protection on a display adapter's video present target.

## -struct-fields

### -field TargetId

[in] The identifier of a display adapter's video present target.

### -field CopyProtectionType

[in] A value from the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enum indicating the type of analog copy protection being requested.

### -field APSTriggerBits

[in] A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.

### -field CopyProtectionSupport

[in] A D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure containing flags indicating the analog copy protection support being requested.

