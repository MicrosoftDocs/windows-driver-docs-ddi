---
UID: NC:d3dkmddi.DXGKDDI_GETPOSTCOMPOSITIONCAPS
title: DXGKDDI_GETPOSTCOMPOSITIONCAPS (d3dkmddi.h)
description: Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling.
old-location: display\dxgkddi_getpostcompositioncaps.htm
ms.assetid: B79959EC-A064-4B35-98EF-5B032AF5D4B4
ms.date: 05/10/2018
ms.keywords: DXGKDDI_GETPOSTCOMPOSITIONCAPS, DXGKDDI_GETPOSTCOMPOSITIONCAPS callback, DXGKDDI_GETPOSTCOMPOSITIONCAPS callback function [Display Devices], d3dkmddi/DXGKDDI_GETPOSTCOMPOSITIONCAPS, display.dxgkddi_getpostcompositioncaps
ms.topic: callback
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
- DXGKDDI_GETPOSTCOMPOSITIONCAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_GETPOSTCOMPOSITIONCAPS callback function


## -description


Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling.


## -parameters




### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pGetPostCompositionCaps

[in] IA pointer to a DXGKARG_GETPOSTCOMPOSITIONCAPS structure that receives the driver capabilities.


## -returns



DXGKDDI_GETPOSTCOMPOSITIONCAPS returns the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|If the routine has been successfully completed.|

 




## -remarks



This function is called at PASSIVE_LEVEL.

The multiplane overlay capabilities are allowed to change due to display configuration changes.




