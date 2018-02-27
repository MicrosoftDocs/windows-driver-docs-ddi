---
UID: NS:dispmprt.DXGK_BRIGHTNESS_INTERFACE_2
title: DXGK_BRIGHTNESS_INTERFACE_2
author: windows-driver-content
description: Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control.
old-location: display\dxgk_brightness_interface_2.htm
old-project: display
ms.assetid: 0c0b877f-cef0-4e98-9f37-60f2d96b81bd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDXGK_BRIGHTNESS_INTERFACE_2, DXGK_BRIGHTNESS_INTERFACE_2, DXGK_BRIGHTNESS_INTERFACE_2 structure [Display Devices], PDXGK_BRIGHTNESS_INTERFACE_2, PDXGK_BRIGHTNESS_INTERFACE_2 structure pointer [Display Devices], display.dxgk_brightness_interface_2, dispmprt/DXGK_BRIGHTNESS_INTERFACE_2, dispmprt/PDXGK_BRIGHTNESS_INTERFACE_2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	Dispmprt.h
apiname:
-	DXGK_BRIGHTNESS_INTERFACE_2
product: Windows
targetos: Windows
req.typenames: DXGK_BRIGHTNESS_INTERFACE_2, *PDXGK_BRIGHTNESS_INTERFACE_2
---

# DXGK_BRIGHTNESS_INTERFACE_2 structure


## -description


Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control.


## -syntax


````
typedef struct {
  USHORT                                     Size;
  USHORT                                     Version;
  PVOID                                      Context;
  PINTERFACE_REFERENCE                       InterfaceReference;
  PINTERFACE_DEREFERENCE                     InterfaceDereference;
  DXGK_BRIGHTNESS_GET_POSSIBLE               GetPossibleBrightness;
  DXGK_BRIGHTNESS_SET                        SetBrightness;
  DXGK_BRIGHTNESS_GET                        GetBrightness;
  DXGK_BRIGHTNESS_GET_CAPS                   GetBrightnessCaps;
  DXGK_BRIGHTNESS_SET_STATE                  SetBrightnessState;
  DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION SetBacklightOptimization;
  DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION    GetBacklightReduction;
} DXGK_BRIGHTNESS_INTERFACE_2, *PDXGK_BRIGHTNESS_INTERFACE_2;
````


## -struct-fields




### -field Size

[in] The size, in bytes, of this structure.


### -field Version

[in] The version number of the brightness interface. Version number constants are defined in Dispmprt.h (for example, <b>DXGK_BRIGHTNESS_INTERFACE_VERSION_2</b>).


### -field Context

[in] A pointer to a private context block.


### -field InterfaceReference

[out] A pointer to an interface reference function that is implemented by the display miniport driver.


### -field InterfaceDereference

[out] A pointer to an interface dereference function that is implemented by the display miniport driver.


### -field GetPossibleBrightness

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_possible.md">DxgkDdiGetPossibleBrightness</a> function.


### -field SetBrightness

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a> function.


### -field GetBrightness

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get.md">DxgkDdiGetBrightness</a> function.


### -field GetBrightnessCaps

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_caps.md">DxgkDdiGetBrightnessCaps</a> function. This function is available starting with Windows 8.


### -field SetBrightnessState

[out] A pointer to the display miniport driver's  <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_state.md">DxgkDdiSetBrightnessState</a> function. This function is available starting with Windows 8.


### -field SetBacklightOptimization

[out] A pointer to the display miniport driver's  <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_backlight_optimization.md">DxgkDdiSetBacklightOptimization</a> function. This function is available starting with Windows 8.


### -field GetBacklightReduction

[out] A pointer to the display miniport driver's  <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_backlight_reduction.md">DxgkDdiGetBacklightReduction</a> function. This function is available starting with Windows 8.


## -remarks



This structure provides additional members, beyond those in the <a href="..\dispmprt\ns-dispmprt-dxgk_brightness_interface.md">DXGK_BRIGHTNESS_INTERFACE</a> interface, that point to driver-implemented functions that control, measure, and optimize display panel brightness and allow smooth brightness control.

For more information on this interface, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj647485">Brightness Control Interface V. 2 (Adaptive and Smooth Brightness Control)</a>.




## -see-also

<a href="..\dispmprt\ns-dispmprt-dxgk_brightness_interface.md">DXGK_BRIGHTNESS_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_INTERFACE_2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

