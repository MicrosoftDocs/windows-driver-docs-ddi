---
UID: NC:d3dkmthk.PDXGK_SET_SHARED_POWER_COMPONENT_STATE
title: PDXGK_SET_SHARED_POWER_COMPONENT_STATE
author: windows-driver-content
description: A callback to indicate whether the specified power component is active.
old-location: display\pdxgk_set_shared_power_component_state.htm
old-project: display
ms.assetid: 779072A4-A82B-4251-93F5-5B6C7ED0598E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PDXGK_SET_SHARED_POWER_COMPONENT_STATE, PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback function [Display Devices], d3dkmthk/PDXGK_SET_SHARED_POWER_COMPONENT_STATE, display.pdxgk_set_shared_power_component_state
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
-	PDXGK_SET_SHARED_POWER_COMPONENT_STATE
product:
- Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback


## -description


A callback to indicate whether the specified power component is active.


## -parameters




### -param DeviceHandle


### -param PrivateHandle


### -param ComponentIndex


### -param Active








#### - GraphicsDeviceHandle

A handle to the graphics device.

A handle to the graphics device.

A handle to the graphics device.


## -returns



Return STATUS_SUCCESS if the call succeeds.



