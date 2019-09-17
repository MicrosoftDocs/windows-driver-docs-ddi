---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 (d3dkmddi.h)
description: Called to change the overlay configuration being displayed.
old-location: display\dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.htm
ms.assetid: B4B6C5F0-AB67-4D30-B6A5-76B7596D22B6
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function [Display Devices], d3dkmddi/DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, display.dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
product:
 - Windows
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function

## -description

Called to change the overlay configuration being displayed.

## -parameters

### -param hAdapter

Identifies the adapter containing the overlay hardware.

### -param pSetVidPnSourceAddressWithMultiPlaneOverlay

A pointer to a DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure that describes the surfaces and display options to present.

## -returns

DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 returns the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|If the routine has completed successfully.|
|STATUS_RETRY|If the driver needs to be called at the PASSIVE_LEVEL. The driver should also set the DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS.PrePresentNeeded flag.|

## -remarks

This function is typically called at interrupt level, but if the driver needs to perform hardware configuration that can only be performed at PASSIVE_LEVEL, the driver can request that this function be recalled at PASSIVE level by returning STATUS_RETRY and setting the DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS.PrePresentNeeded flag.

Even when called at PASSIVE_LEVEL, the driver should avoid spending a significant amount of time in this call because the call blocks the main GPU scheduler thread and delay could lead to present glitches. Time intensive actions should be queued as separate work items by driver and handled in background. In this scenario, any conflicts between the queued item and hardware changes demanded by future pre/post calls should be managed by the driver.

