---
UID: NS:d3dkmddi._DXGKARG_SETTARGETANALOGCOPYPROTECTION
title: "_DXGKARG_SETTARGETANALOGCOPYPROTECTION"
author: windows-driver-content
description: Holds information to set analog copy protection on a display adapter's video present target.
old-location: display\dxgkarg_settargetanalogcopyprotection.htm
old-project: display
ms.assetid: F5A853B2-4A8C-4929-AAEC-28844DEF0B29
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkarg_settargetanalogcopyprotection, DXGKARG_SETTARGETANALOGCOPYPROTECTION, DXGKARG_SETTARGETANALOGCOPYPROTECTION structure [Display Devices], _DXGKARG_SETTARGETANALOGCOPYPROTECTION, d3dkmddi/DXGKARG_SETTARGETANALOGCOPYPROTECTION
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_SETTARGETANALOGCOPYPROTECTION
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETTARGETANALOGCOPYPROTECTION
---

# _DXGKARG_SETTARGETANALOGCOPYPROTECTION structure


## -description


Holds information to set analog copy protection on a display adapter's video present target.


## -syntax


````
typedef struct _DXGKARG_SETTARGETANALOGCOPYPROTECTION {
  D3DDDI_VIDEO_PRESENT_TARGET_ID                    TargetId;
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE    CopyProtectionType;
  UINT                                              APSTriggerBits;
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT CopyProtectionSupport;
} DXGKARG_SETTARGETANALOGCOPYPROTECTION;
````


## -struct-fields




#### - TargetId

[in] The identifier of a display adapter's video present target.


#### - CopyProtectionType

[in] A value from the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enum indicating the type of analog copy protection being requested.


#### - APSTriggerBits

[in] A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.


#### - CopyProtectionSupport

[in] A D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure containing flags indicating the analog copy protection support being requested.

