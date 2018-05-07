---
UID: NS:d3dkmddi._DXGKARG_SETTARGETANALOGCOPYPROTECTION
title: "_DXGKARG_SETTARGETANALOGCOPYPROTECTION"
author: windows-driver-content
description: Holds information to set analog copy protection on a display adapter's video present target.
old-location: display\dxgkarg_settargetanalogcopyprotection.htm
old-project: display
ms.assetid: F5A853B2-4A8C-4929-AAEC-28844DEF0B29
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKARG_SETTARGETANALOGCOPYPROTECTION, DXGKARG_SETTARGETANALOGCOPYPROTECTION structure [Display Devices], _DXGKARG_SETTARGETANALOGCOPYPROTECTION, d3dkmddi/DXGKARG_SETTARGETANALOGCOPYPROTECTION, display.dxgkarg_settargetanalogcopyprotection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_SETTARGETANALOGCOPYPROTECTION
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_SETTARGETANALOGCOPYPROTECTION
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

