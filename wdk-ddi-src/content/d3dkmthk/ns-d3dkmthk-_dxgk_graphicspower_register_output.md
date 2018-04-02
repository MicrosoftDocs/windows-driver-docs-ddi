---
UID: NS:d3dkmthk._DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
title: "_DXGK_GRAPHICSPOWER_REGISTER_OUTPUT"
author: windows-driver-content
description: A structure containing output data used to manage shared power components.
old-location: display\dxgk_graphicspower_register_output.htm
old-project: display
ms.assetid: 13F74BB4-91FE-4B5C-B0EB-B3524D0BD959
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT structure [Display Devices], PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT structure pointer [Display Devices], _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, d3dkmthk/DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, d3dkmthk/PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, display.dxgk_graphicspower_register_output"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
product: Windows
targetos: Windows
req.typenames: DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT structure


## -description


A structure containing output data used to manage shared power components.


## -struct-fields




### -field DeviceHandle

An opaque handle that should be provided when making callbacks to the graphics device.


### -field InitialGrfxPowerState

The power state of the graphics device represented by the DeviceHandle at the time of internal IOCTL handling.


### -field SetSharedPowerComponentStateCb

A callback to indicate whether the specified power component is active.  The component index should match the index used by the graphics driver when the component was indicated at driver initialization and the component must be one of the shared power component types. If this callback is used to set a state which has already been set by this driver for this graphics device, the call will have no effect. If setting a component active, the graphics driver will be notified synchronously before this callback returns.


### -field UnregisterCb

 A callback to un-register itself with the graphics driver.  All shared power components should no longer be active.  The system will behave as if SetSharedPowerComponentStateCb had been called for all active shared power components with a new active state of FALSE.  Upon return, previously provided callbacks can no longer be used.

