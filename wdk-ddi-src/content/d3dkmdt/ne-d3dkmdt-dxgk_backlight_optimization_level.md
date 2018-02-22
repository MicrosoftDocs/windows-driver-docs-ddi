---
UID: NE:d3dkmdt.DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
title: DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
author: windows-driver-content
description: Indicates the optimization level of brightness control. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.
old-location: display\dxgk_backlight_optimization_level.htm
old-project: display
ms.assetid: 8ad096bb-0012-40fc-a038-2f25d6a59b43
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXGK_BACKLIGHT_OPTIMIZATION_LEVEL enumeration [Display Devices], display.dxgk_backlight_optimization_level, d3dkmdt/DxgkBacklightOptimizationDisable, DxgkBacklightOptimizationDynamic, DXGK_BACKLIGHT_OPTIMIZATION_LEVEL, d3dkmdt/DxgkBacklightOptimizationEDR, DxgkBacklightOptimizationDisable, d3dkmdt/DxgkBacklightOptimizationDimmed, DxgkBacklightOptimizationEDR, d3dkmdt/DxgkBacklightOptimizationDesktop, DxgkBacklightOptimizationDimmed, d3dkmdt/DXGK_BACKLIGHT_OPTIMIZATION_LEVEL, d3dkmdt/DxgkBacklightOptimizationDynamic, DxgkBacklightOptimizationDesktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmdt.h
apiname:
-	DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
product: Windows
targetos: Windows
req.typenames: DXGK_BACKLIGHT_OPTIMIZATION_LEVEL
---

# DXGK_BACKLIGHT_OPTIMIZATION_LEVEL enumeration


## -description


Indicates the optimization level of brightness control. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.


## -syntax


````
typedef enum  { 
  DxgkBacklightOptimizationDisable  = 0,
  DxgkBacklightOptimizationDesktop  = 1,
  DxgkBacklightOptimizationDynamic  = 2,
  DxgkBacklightOptimizationDimmed   = 3,
  DxgkBacklightOptimizationEDR      = 4
} DXGK_BACKLIGHT_OPTIMIZATION_LEVEL;
````


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



For more information on usage scenarios involving <b>DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</b> enumeration values, see Remarks in the <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_backlight_optimization.md">DxgkDdiSetBacklightOptimization</a> function.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_backlight_optimization.md">DxgkDdiSetBacklightOptimization</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BACKLIGHT_OPTIMIZATION_LEVEL enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

