---
UID: NC:d3dkmthk.PDXGK_GRAPHICSPOWER_UNREGISTER
title: PDXGK_GRAPHICSPOWER_UNREGISTER (d3dkmthk.h)
description: A callback to un-register itself with the graphics driver.
old-location: display\pdxgk_graphicspower_unregister.htm
ms.assetid: A925D5D3-EF79-4C14-BE1C-188C255DDF8E
ms.date: 04/16/2018
keywords: ["PDXGK_GRAPHICSPOWER_UNREGISTER callback function"]
ms.keywords: PDXGK_GRAPHICSPOWER_UNREGISTER, PDXGK_GRAPHICSPOWER_UNREGISTER callback, PDXGK_GRAPHICSPOWER_UNREGISTER callback function [Display Devices], d3dkmthk/PDXGK_GRAPHICSPOWER_UNREGISTER, display.pdxgk_graphicspower_unregister
f1_keywords:
 - "d3dkmthk/PDXGK_GRAPHICSPOWER_UNREGISTER"
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
- PDXGK_GRAPHICSPOWER_UNREGISTER
product:
- Windows
targetos: Windows
tech.root: display
req.typenames:
---

# PDXGK_GRAPHICSPOWER_UNREGISTER callback function


## -description


A callback to un-register itself with the graphics driver.


## -parameters




### -param DeviceHandle

An opaque handle which should be provided when making callbacks to the graphics device.


### -param PrivateHandle

An opaque handle which will be provided in any callbacks. This handle must be globally unique, therefore, a pointer to the calling driver’s PDO or FDO should be used.


## -returns



Return STATUS_SUCCESS if the call succeeds.



