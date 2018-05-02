---
UID: NS:d3dkmddi._DXGKARG_SETTARGETGAMMA
title: "_DXGKARG_SETTARGETGAMMA"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_SETTARGETGAMMA.
old-location: display\dxgkarg_settargetgamma.htm
old-project: display
ms.assetid: 94BA40BD-3B56-44EF-BAD4-49556E68C550
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKARG_SETTARGETGAMMA, DXGKARG_SETTARGETGAMMA structure [Display Devices], PDXGKARG_SETTARGETGAMMA, PDXGKARG_SETTARGETGAMMA structure pointer [Display Devices], _DXGKARG_SETTARGETGAMMA, d3dkmddi/DXGKARG_SETTARGETGAMMA, d3dkmddi/PDXGKARG_SETTARGETGAMMA, display.dxgkarg_settargetgamma
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
-	DXGKARG_SETTARGETGAMMA
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_SETTARGETGAMMA
---

# _DXGKARG_SETTARGETGAMMA structure


## -description


Used to hold the arguments for <a href="https://msdn.microsoft.com/658EA0AA-80FC-4A45-B2EF-DFE928917E7B">DXGKDDI_SETTARGETGAMMA</a>.


## -struct-fields




### -field TargetId

The identifier of a display adapter's video present target.


### -field GammaRamp

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546014">D3DKMDT_GAMMA_RAMP</a> struct which describes the type of gamma ramp to set and the buffer containing the ramp data.

