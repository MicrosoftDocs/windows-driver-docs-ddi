---
UID: NC:d3dkmthk.PDXGK_SET_SHARED_POWER_COMPONENT_STATE
title: PDXGK_SET_SHARED_POWER_COMPONENT_STATE
author: windows-driver-content
description: A callback to indicate whether the specified power component is active.
old-location: display\pdxgk_set_shared_power_component_state.htm
tech.root: display
ms.assetid: 779072A4-A82B-4251-93F5-5B6C7ED0598E
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PDXGK_SET_SHARED_POWER_COMPONENT_STATE, PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback, PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback function [Display Devices], d3dkmthk/PDXGK_SET_SHARED_POWER_COMPONENT_STATE, display.pdxgk_set_shared_power_component_state
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
req.typenames:
---

# PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback function


## -description


A callback to indicate whether the specified power component is active.


## -parameters




### -param DeviceHandle

An opaque handle which should be provided when making callbacks to the graphics device.

### -param PrivateHandle

An opaque handle which will be provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver’s PDO or FDO should be used.

### -param ComponentIndex

The index of the component. Generally, this will be the index used by the graphics adapter. The exception is for LDA scenarios, where the HIWORD of the ComponentIndex indicates the adapter index, as is done when the graphics driver is called by graphics kernel for F-state changes in LDA scenarios.

### -param Active

Specifies whether the shared power component state is active.





## -returns



Return STATUS_SUCCESS if the call succeeds.



