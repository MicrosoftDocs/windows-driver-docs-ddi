---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION
title: DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION (dispmprt.h)
description: Called by the Microsoft DirectX graphics kernel subsystem to set the level of optimization that the display miniport driver uses to control the brightness of an integrated display panel.
old-location: display\dxgkddisetbacklightoptimization.htm
tech.root: display
ms.assetid: b8c37df8-ba86-4cfd-add0-49ba9c90f04a
ms.date: 05/10/2018
ms.keywords: DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION, DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION callback, DxgkDdiSetBacklightOptimization, DxgkDdiSetBacklightOptimization callback function [Display Devices], display.dxgkddisetbacklightoptimization, dispmprt/DxgkDdiSetBacklightOptimization
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
-	DxgkDdiSetBacklightOptimization
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION callback function


## -description


Called by the Microsoft DirectX graphics kernel subsystem to set the level of optimization that the display miniport driver uses to control the brightness of an integrated display panel.


## -parameters




### -param Context [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param OptimizationLevel [in]

A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/jj128358">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a> that indicates the optimization level of brightness control.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



The display miniport driver can dynamically change the backlight optimization level of the integrated display panel based upon the current content on the screen.

The driver must respond to requests from the operating system to change the backlight optimization level in the <i>OptimizationLevel</i> parameter. Such requests are based upon system state changes.

After the driver has enabled adaptive brightness on the display panel in response to a call to the <a href="https://msdn.microsoft.com/804046ff-0cc7-4ff0-be07-b574cb40fd2b">DxgkDdiSetBrightnessState</a> function, it must not disable adaptive brightness.

When the driver transitions from one backlight optimization level to another, it should make a gradual transition in brightness settings of the integrated display panel. An important  example of this type of transition is when a user adjusts video playback controls and the operating system responds by resetting the value of <i>OptimizationLevel</i> from <b>DxgkBacklightOptimizationDynamic</b> to <b>DxgkBacklightOptimizationDesktop</b>.

Connecting additional display devices to the system must not compromise the ability of the driver to perform adaptive brightness control on the integrated display panel.

This function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj128358">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/804046ff-0cc7-4ff0-be07-b574cb40fd2b">DxgkDdiSetBrightnessState</a>
 

 

