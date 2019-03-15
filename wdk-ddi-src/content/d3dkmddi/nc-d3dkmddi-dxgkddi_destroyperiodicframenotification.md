---
UID: NC:d3dkmddi.DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION
title: DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION (d3dkmddi.h)
description: Used to destroy a periodic frame notification.
old-location: display\dxgkddi_destroyperiodicframenotification.htm
ms.assetid: 4C6B6FB2-A699-40F5-ACA3-62E8620E99AB
ms.date: 05/10/2018
ms.keywords: DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION, DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION callback, DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION callback function [Display Devices], d3dkmddi/DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION, display.dxgkddi_destroyperiodicframenotification
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
- DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION callback function


## -description


Used to destroy a periodic frame notification.


## -parameters




### -param pDestroyPeriodicFrameNotification [in]

A structure of type <i>PDXGKARG_DESTROYPERIODICFRAMENOTIFICATION</i> containing the arguments needed to destroy a periodic frame notification.


## -returns



DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|When a periodic frame notification has been successfully created.|
|STATUS_INVALID_PARAMETER|Indicates that there was an invalid parameter passed to the call.|
