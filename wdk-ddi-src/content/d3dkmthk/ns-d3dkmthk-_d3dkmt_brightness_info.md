---
UID: NS:d3dkmthk._D3DKMT_BRIGHTNESS_INFO
title: "_D3DKMT_BRIGHTNESS_INFO"
author: windows-driver-content
description: Contains information about the brightness of an integrated display panel.
old-location: display\d3dkmt_brightness_info.htm
old-project: display
ms.assetid: a620b0b2-85ce-4373-a50c-299d8ce7a91c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_BRIGHTNESS_INFO, D3DKMT_BRIGHTNESS_INFO structure [Display Devices], _D3DKMT_BRIGHTNESS_INFO, d3dkmthk/D3DKMT_BRIGHTNESS_INFO, display.d3dkmt_brightness_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMT_BRIGHTNESS_INFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_BRIGHTNESS_INFO
---

# _D3DKMT_BRIGHTNESS_INFO structure


## -description


Contains information about the brightness of an integrated display panel.


## -struct-fields




### -field Type

A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/jj128342">D3DKMT_BRIGHTNESS_INFO_TYPE</a> that  indicates the type of brightness information to retrieve or set.


### -field PossibleLevels

A <a href="https://msdn.microsoft.com/library/windows/hardware/jj128343">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a> structure that contains information about all possible brightness levels that the integrated display panel supports.


### -field Brightness

The current brightness level.


### -field BrightnessCaps

A <a href="https://msdn.microsoft.com/library/windows/hardware/jj128359">DXGK_BRIGHTNESS_CAPS</a> structure that represents the brightness control capabilities of the integrated display panel.


### -field BrightnessState

A <a href="https://msdn.microsoft.com/library/windows/hardware/jj128361">DXGK_BRIGHTNESS_STATE</a> structure that represents the smooth brightness control capabilities of the integrated display panel.


### -field OptimizationLevel

A <a href="https://msdn.microsoft.com/library/windows/hardware/jj128358">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a> structure that represents the optimization level of brightness control.


### -field ReductionInfo

A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/jj128357">DXGK_BACKLIGHT_INFO</a> that provides the current absolute level of backlight reduction.


### -field VerboseLogging

A boolean value that indicates whether Event Tracing for Windows (ETW) logging of brightness information should be verbose.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj128342">D3DKMT_BRIGHTNESS_INFO_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj128343">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj128357">DXGK_BACKLIGHT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj128358">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj128359">DXGK_BRIGHTNESS_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj128361">DXGK_BRIGHTNESS_STATE</a>
 

 

