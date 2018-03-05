---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION
title: DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION
author: windows-driver-content
description: Called by the Microsoft DirectX graphics kernel subsystem to set the level of optimization that the display miniport driver uses to control the brightness of an integrated display panel.
old-location: display\dxgkddisetbacklightoptimization.htm
old-project: display
ms.assetid: b8c37df8-ba86-4cfd-add0-49ba9c90f04a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION, DxgkDdiSetBacklightOptimization, DxgkDdiSetBacklightOptimization callback function [Display Devices], display.dxgkddisetbacklightoptimization, dispmprt/DxgkDdiSetBacklightOptimization
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION callback


## -description


Called by the Microsoft DirectX graphics kernel subsystem to set the level of optimization that the display miniport driver uses to control the brightness of an integrated display panel.


## -prototype


````
DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION DxgkDdiSetBacklightOptimization;

NTSTATUS* DxgkDdiSetBacklightOptimization(
  _In_ PVOID                             Context,
  _In_ DXGK_BACKLIGHT_OPTIMIZATION_LEVEL OptimizationLevel
)
{ ... }
````


## -parameters




### -param Context [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param OptimizationLevel [in]

A value of type <a href="..\d3dkmdt\ne-d3dkmdt-dxgk_backlight_optimization_level.md">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a> that indicates the optimization level of brightness control.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



The display miniport driver can dynamically change the backlight optimization level of the integrated display panel based upon the current content on the screen.

The driver must respond to requests from the operating system to change the backlight optimization level in the <i>OptimizationLevel</i> parameter. Such requests are based upon system state changes.

After the driver has enabled adaptive brightness on the display panel in response to a call to the <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_state.md">DxgkDdiSetBrightnessState</a> function, it must not disable adaptive brightness.

When the driver transitions from one backlight optimization level to another, it should make a gradual transition in brightness settings of the integrated display panel. An important  example of this type of transition is when a user adjusts video playback controls and the operating system responds by resetting the value of <i>OptimizationLevel</i> from <b>DxgkBacklightOptimizationDynamic</b> to <b>DxgkBacklightOptimizationDesktop</b>.

Connecting additional display devices to the system must not compromise the ability of the driver to perform adaptive brightness control on the integrated display panel.

This function should be made pageable.




## -see-also

<a href="..\d3dkmdt\ne-d3dkmdt-dxgk_backlight_optimization_level.md">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_state.md">DxgkDdiSetBrightnessState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

