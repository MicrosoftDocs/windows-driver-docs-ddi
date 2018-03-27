---
UID: NC:d3dkmthk.PDXGK_GRAPHICSPOWER_UNREGISTER
title: PDXGK_GRAPHICSPOWER_UNREGISTER
author: windows-driver-content
description: A callback to un-register itself with the graphics driver.
old-location: display\pdxgk_graphicspower_unregister.htm
old-project: display
ms.assetid: A925D5D3-EF79-4C14-BE1C-188C255DDF8E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PDXGK_GRAPHICSPOWER_UNREGISTER, PDXGK_GRAPHICSPOWER_UNREGISTER callback function [Display Devices], d3dkmthk/PDXGK_GRAPHICSPOWER_UNREGISTER, display.pdxgk_graphicspower_unregister
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
-	PDXGK_GRAPHICSPOWER_UNREGISTER
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PDXGK_GRAPHICSPOWER_UNREGISTER callback


## -description


A callback to un-register itself with the graphics driver.  


## -parameters




### -param DeviceHandle

A handle to the graphics device.


### -param PrivateHandle

A handle to the graphics device.


## -returns



Return STATUS_SUCCESS if the call succeeds.



