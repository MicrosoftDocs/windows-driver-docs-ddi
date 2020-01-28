---
UID: NC:d3dkmthk.PDXGK_POWER_NOTIFICATION
title: PDXGK_POWER_NOTIFICATION (d3dkmthk.h)
description: A callback providing notification that the graphics device will be undergoing a device power state transition.
old-location: display\pdxgk_power_notification.htm
ms.assetid: 11549B4E-7929-4957-9775-BF8AAF501D45
ms.date: 03/29/2018
ms.keywords: "*PDXGK_POWER_NOTIFICATION, *PDXGK_POWER_NOTIFICATION callback function [Display Devices], d3dkmthk/*PDXGK_POWER_NOTIFICATION, display.pdxgk_power_notification"
f1_keywords:
 - "d3dkmthk/*PDXGK_POWER_NOTIFICATION"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmthk.h
api_name:
- *PDXGK_POWER_NOTIFICATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PDXGK_POWER_NOTIFICATION callback


## -description


A callback providing notification that the graphics device will be undergoing a device power state transition.


## -parameters




### -param GraphicsDeviceHandle

An opaque handle which should be provided when making callbacks to the graphics device.


### -param NewGrfxPowerState

Indicates the new graphics power state that is in the process of being set.


### -param PreNotification

Indicates that a notification should be provided.


### -param PrivateHandle

An opaque handle which will be provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver’s PDO or FDO should be used.






## -returns



This callback function does not return a value.



## -remarks

This callback is made at PASSIVE_LEVEL. The driver may block in order to complete the servicing of the operation only when the new power state is PowerDeviceD3. In this case, the call must still be completed in a timely fashion, as it can block the completion of the overall device power state transition and is subject to causing a power watchdog bug check. The driver must not block when the new state is PowerDeviceD0. When going into PowerDeviceD3, both a “pre” and “post” notification will be provided, assuming that the transition is not canceled in the interim. When going into PowerDeviceD0, only a “post” notification will be provided. It is permitted for this callback handler to call the SetSharedPowerComponentStateCb graphics callback if desired; no other callbacks into graphics kernel are permitted from this handler.

> [!Important] 
> The initial graphics power state will be provided in the IOCTL output, however, since it is possible that the graphics device may be undergoing a power state transition while registration is occurring, a mutex must be acquired around the IOCTL call and parsing of the original state, and that same mutex must be acquired in this callback function. That way, should the state be transitioning, the callback will provide the most up to date state information.

The following
