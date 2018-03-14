---
UID: NS:d3dkmdt._DXGK_BACKLIGHT_INFO
title: "_DXGK_BACKLIGHT_INFO"
author: windows-driver-content
description: Contains the current level of backlight reduction that is applied to the integrated display panel. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.
old-location: display\dxgk_backlight_info.htm
old-project: display
ms.assetid: 9008e5e6-e03c-4d34-99bd-3e6624327fcc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_BACKLIGHT_INFO, DXGK_BACKLIGHT_INFO structure [Display Devices], _DXGK_BACKLIGHT_INFO, d3dkmdt/DXGK_BACKLIGHT_INFO, display.dxgk_backlight_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmdt.h
api_name:
-	DXGK_BACKLIGHT_INFO
product: Windows
targetos: Windows
req.typenames: DXGK_BACKLIGHT_INFO
---

# _DXGK_BACKLIGHT_INFO structure


## -description


Contains the current level of backlight reduction that is applied to the integrated display panel. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive brightness control.


## -syntax


````
typedef struct _DXGK_BACKLIGHT_INFO {
  USHORT                        BacklightUsersetting;
  USHORT                        BacklightEffective;
  D3DDDI_GAMMA_RAMP_RGB256x3x16 GammaRamp;
} DXGK_BACKLIGHT_INFO;
````


## -struct-fields




### -field BacklightUsersetting

[out] The absolute brightness level in hardware that corresponds to the current percent brightness level requested by the operating system.

This member can range in value from 0 to 65535.


### -field BacklightEffective

[out] The absolute brightness level in hardware that is currently set by the display miniport drive for adaptive brightness control.

This member can range in value from 0 to 65535.


### -field GammaRamp

[out] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16.md">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> structure that contains a description of a gamma lookup table.
This lookup table represents the gamma ramp that has been optimized for backlight display by the display miniport driver from a gamma ramp set by an application.


## -remarks



For more information about the use of this structure, see Remarks of the <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_backlight_reduction.md">DxgkDdiGetBacklightReduction</a> function.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_backlight_reduction.md">DxgkDdiGetBacklightReduction</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16.md">D3DDDI_GAMMA_RAMP_RGB256x3x16</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BACKLIGHT_INFO structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

