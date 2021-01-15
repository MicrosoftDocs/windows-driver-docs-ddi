---
UID: NS:d3dkmddi._DXGKARG_SETTARGETGAMMA
title: _DXGKARG_SETTARGETGAMMA (d3dkmddi.h)
description: Used to hold the arguments for DXGKDDI_SETTARGETGAMMA.
old-location: display\dxgkarg_settargetgamma.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_SETTARGETGAMMA structure"]
ms.keywords: DXGKARG_SETTARGETGAMMA, DXGKARG_SETTARGETGAMMA structure [Display Devices], PDXGKARG_SETTARGETGAMMA, PDXGKARG_SETTARGETGAMMA structure pointer [Display Devices], _DXGKARG_SETTARGETGAMMA, d3dkmddi/DXGKARG_SETTARGETGAMMA, d3dkmddi/PDXGKARG_SETTARGETGAMMA, display.dxgkarg_settargetgamma
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
req.typenames: DXGKARG_SETTARGETGAMMA
f1_keywords:
 - _DXGKARG_SETTARGETGAMMA
 - d3dkmddi/_DXGKARG_SETTARGETGAMMA
 - DXGKARG_SETTARGETGAMMA
 - d3dkmddi/DXGKARG_SETTARGETGAMMA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETTARGETGAMMA
 - DXGKARG_SETTARGETGAMMA
---

# _DXGKARG_SETTARGETGAMMA structure


## -description

Used to hold the arguments for <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_settargetgamma">DXGKDDI_SETTARGETGAMMA</a>.

## -struct-fields

### -field TargetId

The identifier of a display adapter's video present target.

### -field GammaRamp

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_gamma_ramp">D3DKMDT_GAMMA_RAMP</a> struct which describes the type of gamma ramp to set and the buffer containing the ramp data.

