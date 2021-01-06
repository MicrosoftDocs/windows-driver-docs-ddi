---
UID: NC:d3dkmddi.DXGKDDI_GETMULTIPLANEOVERLAYCAPS
title: DXGKDDI_GETMULTIPLANEOVERLAYCAPS (d3dkmddi.h)
description: Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes.
old-location: display\dxgkddi_getmultiplaneoverlaycaps.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback function"]
ms.keywords: DXGKDDI_GETMULTIPLANEOVERLAYCAPS, DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback, DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback function [Display Devices], d3dkmddi/DXGKDDI_GETMULTIPLANEOVERLAYCAPS, display.dxgkddi_getmultiplaneoverlaycaps
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
req.typenames: 
f1_keywords:
 - DXGKDDI_GETMULTIPLANEOVERLAYCAPS
 - d3dkmddi/DXGKDDI_GETMULTIPLANEOVERLAYCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_GETMULTIPLANEOVERLAYCAPS
product:
 - Windows
---

# DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback function


## -description

Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes.

## -parameters

### -param hAdapter

[in] Identifies the adapter containing the overlay hardware.

### -param pGetMultiPlaneOverlayCaps

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getmultiplaneoverlaycaps">DXGKARG_GETMULTIPLANEOVERLAYCAPS</a> structure that receives the driver capabilities.

## -returns

DXGKDDI_GETMULTIPLANEOVERLAYCAPS returns the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|If the routine has been successfully completed.|

## -remarks

This function is called at PASSIVE_LEVEL.

The multiplane overlay capabilities are allowed to change due to display configuration changes.

For WDDM 2.2 drivers, this DDI is used to retrieve the multiplane overlay capabilities rather than the user mode DDIs.
