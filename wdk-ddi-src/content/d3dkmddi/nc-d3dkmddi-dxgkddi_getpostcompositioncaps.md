---
UID: NC:d3dkmddi.DXGKDDI_GETPOSTCOMPOSITIONCAPS
title: DXGKDDI_GETPOSTCOMPOSITIONCAPS
author: windows-driver-content
description: Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling.
old-location: display\dxgkddi_getpostcompositioncaps.htm
old-project: display
ms.assetid: B79959EC-A064-4B35-98EF-5B032AF5D4B4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDDI_GETPOSTCOMPOSITIONCAPS
req.alt-loc: d3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_GETPOSTCOMPOSITIONCAPS callback



## -description
Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling.



## -prototype

````
NTSTATUS APIENTRY DXGKDDI_GETPOSTCOMPOSITIONCAPS(
  _In_ const HANDLE                          hAdapter,
  _In_ const PDXGKARG_GETPOSTCOMPOSITIONCAPS pGetPostCompositonCaps
);
````


## -parameters

### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pGetPostCompositonCaps [in]

IA pointer to a DXGKARG_GETPOSTCOMPOSITIONCAPS structure that receives the driver capabilities.


## -returns
DXGKDDI_GETPOSTCOMPOSITIONCAPS returns the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>If the routine has been successfully completed.

 


## -remarks
This function is called at PASSIVE_LEVEL.

The multiplane overlay capabilities are allowed to change due to display configuration changes.
</p>