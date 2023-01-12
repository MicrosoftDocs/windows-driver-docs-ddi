---
UID: NC:d3dkmthk.PDXGK_REMOVAL_NOTIFICATION
title: PDXGK_REMOVAL_NOTIFICATION (d3dkmthk.h)
description: A callback indicating that the graphics device is being removed.
old-location: display\pdxgk_removal_notification.htm
ms.date: 10/07/2022
keywords: ["PDXGK_REMOVAL_NOTIFICATION callback -remarks"]
ms.keywords: "*PDXGK_REMOVAL_NOTIFICATION, *PDXGK_REMOVAL_NOTIFICATION callback function [Display Devices], d3dkmthk/*PDXGK_REMOVAL_NOTIFICATION, display.pdxgk_removal_notification"
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
tech.root: display
ms.custom: engagement-fy23
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
f1_keywords:
 - PDXGK_REMOVAL_NOTIFICATION
 - d3dkmthk/PDXGK_REMOVAL_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PDXGK_REMOVAL_NOTIFICATION
---

# PDXGK_REMOVAL_NOTIFICATION callback

## -description

A callback indicating that the graphics device is being removed.

## -parameters

### -param GraphicsDeviceHandle

An opaque handle which should be provided when making callbacks to the graphics device.

### -param PrivateHandle

An opaque handle which will be provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver's PDO or FDO should be used.

## -remarks

Removal can occur on driver uninstall, device disable, device fault, and surprise removal. This callback is made at PASSIVE_LEVEL.
