---
UID: NC:d3dkmthk.PDXGK_POWER_NOTIFICATION
title: PDXGK_POWER_NOTIFICATION
author: windows-driver-content
description: A callback providing notification that the graphics device will be undergoing a device power state transition.
old-location: display\pdxgk_power_notification.htm
old-project: display
ms.assetid: 11549B4E-7929-4957-9775-BF8AAF501D45
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_POWER_NOTIFICATION, *PDXGK_POWER_NOTIFICATION callback function [Display Devices], d3dkmthk/*PDXGK_POWER_NOTIFICATION, display.pdxgk_power_notification"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
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
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	*PDXGK_POWER_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PDXGK_POWER_NOTIFICATION callback


## -description


A callback providing notification that the graphics device will be undergoing a device power state transition.


## -prototype


````
VOID *PDXGK_POWER_NOTIFICATION(
   PVOID              GraphicsDeviceHandle,
   DEVICE_POWER_STATE NewGrfxPowerState,
   BOOLEAN            PreNotification
);
````


## -parameters




### -param GraphicsDeviceHandle

A handle to the graphics device.


### -param NewGrfxPowerState

Indicates the new graphics power state.


### -param PreNotification

Indicates that a notification should be provided.


### -param PrivateHandle








## -returns



This callback function does not return a value.



