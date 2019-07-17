---
UID: NC:d3dkmddi.DXGKDDI_SETTARGETANALOGCOPYPROTECTION
title: DXGKDDI_SETTARGETANALOGCOPYPROTECTION (d3dkmddi.h)
description: Sets the analog copy protection on the specified target id. This is functionally equivalent to the DxgkDdiUpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION is changed.
old-location: display\dxgkddi_settargetanalogcopyprotection.htm
ms.assetid: D41A1867-C654-4747-B804-CAE047025458
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETTARGETANALOGCOPYPROTECTION, DXGKDDI_SETTARGETANALOGCOPYPROTECTION callback, DXGKDDI_SETTARGETANALOGCOPYPROTECTION callback function [Display Devices], d3dkmddi/DXGKDDI_SETTARGETANALOGCOPYPROTECTION, display.dxgkddi_settargetanalogcopyprotection
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKDDI_SETTARGETANALOGCOPYPROTECTION"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DXGKDDI_SETTARGETANALOGCOPYPROTECTION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETTARGETANALOGCOPYPROTECTION callback function


## -description


Sets the analog copy protection on the specified target id.  This is functionally equivalent to the DxgkDdiUpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION is changed.


## -parameters




### -param hAdapter [in]

Identifies the adapter.


### -param pSetTargetAnalogCopyProtectionArg [in]

A pointer to a DXGKARG_SETTARGETANALOGCOPYPROTECTION structure that provides the target id and the analog content protection parameters being requested.


## -returns



If this routine succeeds, it returns STATUS_SUCCESS. 




## -remarks



This is an optional DDI so the function pointer in the DRIVER_INITIALIZATION_DATA should be set to null if the DDI is not implemented for every adapter supported by the driver.  Since analog content protection is only supported on analog targets and may not be supported through dongles it is increasingly likely over time that drivers will have no need to support this DDI.


The OEMCopyProtection byte array which is part of the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure used in the old DDI has been dropped as it was reserved and never defined so always contained zeroes.  



This function is always called at PASSIVE level so the supporting code should be made pageable.



