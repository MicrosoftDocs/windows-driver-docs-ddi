---
UID: NE:d3dkmdt.DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
title: DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
author: windows-driver-content
description: Indicates the optimization level of brightness control. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.
old-location: display\dxgk_backlight_optimization_level.htm
old-project: display
ms.assetid: 8ad096bb-0012-40fc-a038-2f25d6a59b43
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_BACKLIGHT_OPTIMIZATION_LEVEL, DXGK_BACKLIGHT_OPTIMIZATION_LEVEL enumeration [Display Devices], DxgkBacklightOptimizationDesktop, DxgkBacklightOptimizationDimmed, DxgkBacklightOptimizationDisable, DxgkBacklightOptimizationDynamic, DxgkBacklightOptimizationEDR, d3dkmdt/DXGK_BACKLIGHT_OPTIMIZATION_LEVEL, d3dkmdt/DxgkBacklightOptimizationDesktop, d3dkmdt/DxgkBacklightOptimizationDimmed, d3dkmdt/DxgkBacklightOptimizationDisable, d3dkmdt/DxgkBacklightOptimizationDynamic, d3dkmdt/DxgkBacklightOptimizationEDR, display.dxgk_backlight_optimization_level
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmdt.h
api_name:
-	DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
product: Windows
targetos: Windows
req.typenames: DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
---

# DXGK_BACKLIGHT_OPTIMIZATION_LEVEL enumeration


## -description


Indicates the optimization level of brightness control. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.


## -enum-fields




### -field DxgkBacklightOptimizationDisable

The display miniport driver must completely disable adaptive brightness control.

The operating system always sets this value if the system is on AC power.


### -field DxgkBacklightOptimizationDesktop

The display miniport driver should optimize backlight settings for desktop presentation when the system is on DC power and the other possible scenarios (disabled, dynamic, and dimmed) are not active. This type of optimization is appropriate for displaying photos, internet browsers, common document types, and video playback controls.

This is the default adaptive brightness setting when the system is on DC power.


### -field DxgkBacklightOptimizationDynamic

The display miniport driver should optimize backlight settings for presentation of full-screen video. Typical playback scenarios include playing movies and full-screen video. 

The operating system sets this value if a full-screen Windows App is using the HTML5 video tag with JavaScript or the <a href="https://msdn.microsoft.com/5146a1d4-17f0-4da2-a8ba-b121f9beeb21">MediaElement</a> control with XAML.

The operating system sets this value only when only full-screen video content is displayed on the screen. This value is not set if playback controls or charms are displayed during video playback; in this case, adaptive brightness will not be enabled.


### -field DxgkBacklightOptimizationDimmed

The display miniport driver should optimize backlight settings to display at a low light level that is still visible even if it is not easily readable. In this scenario the display is typically set to a 30 percent brightness level.

After a defined period of no user input, the operating system sets this value to dim the display.


### -field DxgkBacklightOptimizationEDR

Optimization level which informs the driver that the display is being driven with either High Dynamic Range or Enhanced Dynamic Range content so any backlight optimizations can be tailored to the scenario.                                                                                                                                                                                                                                                                                                         


## -remarks



For more information on usage scenarios involving <b>DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</b> enumeration values, see Remarks in the <a href="https://msdn.microsoft.com/b8c37df8-ba86-4cfd-add0-49ba9c90f04a">DxgkDdiSetBacklightOptimization</a> function.




## -see-also




<a href="https://msdn.microsoft.com/b8c37df8-ba86-4cfd-add0-49ba9c90f04a">DxgkDdiSetBacklightOptimization</a>
 

 

