---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_STATE
title: DXGK_BRIGHTNESS_SET_STATE (dispmprt.h)
description: Enables smooth brightness control on an integrated display panel.
old-location: display\dxgkddisetbrightnessstate.htm
tech.root: display
ms.assetid: 804046ff-0cc7-4ff0-be07-b574cb40fd2b
ms.date: 05/10/2018
ms.keywords: DXGK_BRIGHTNESS_SET_STATE, DXGK_BRIGHTNESS_SET_STATE callback, DxgkDdiSetBrightnessState, DxgkDdiSetBrightnessState callback function [Display Devices], display.dxgkddisetbrightnessstate, dispmprt/DxgkDdiSetBrightnessState
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkDdiSetBrightnessState
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGK_BRIGHTNESS_SET_STATE callback function


## -description


Enables smooth brightness control on an integrated display panel.


## -parameters




### -param Context [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param *BrightnessState [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/jj128361">DXGK_BRIGHTNESS_STATE</a> structure that indicates that the display miniport driver should enable the smooth brightness control for the integrated display panel.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



For the operating system to be able to adjust screen brightness smoothly, starting with Windows 8 the display miniport driver must report 10 brightness levels, expressed from 0 to 100 percent. At a level of zero percent, the screen contents should be barely visible to the user. A level of 100 percent is the maximum brightness that the integrated display panel can produce. The driver and hardware can support finer brightness control for internal operations.

When the <a href="https://msdn.microsoft.com/83609679-20df-463d-ac3a-bb8a87897608">DxgkDdiSetBrightness</a> function is called, the driver should select an appropriate slope to provide a smooth brightness transition based on panel characteristics, but any transition must complete in under 500 milliseconds.

This function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/83609679-20df-463d-ac3a-bb8a87897608">DxgkDdiSetBrightness</a>
 

 

