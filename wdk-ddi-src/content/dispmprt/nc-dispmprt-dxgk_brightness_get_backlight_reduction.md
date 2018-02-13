---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION
title: DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION
author: windows-driver-content
description: Retrieves the current level of backlight reduction that is applied to the integrated display panel.
old-location: display\dxgkddigetbacklightreduction.htm
old-project: display
ms.assetid: 018cb4a0-e71d-407e-8fe9-716312099b73
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddigetbacklightreduction, DxgkDdiGetBacklightReduction callback function [Display Devices], DxgkDdiGetBacklightReduction, DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION, DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION, dispmprt/DxgkDdiGetBacklightReduction
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dispmprt.h
apiname:
-	DxgkDdiGetBacklightReduction
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback


## -description


Retrieves the current level of backlight reduction that is applied to the integrated display panel.


## -prototype


````
DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION DxgkDdiGetBacklightReduction;

NTSTATUS* DxgkDdiGetBacklightReduction(
  _In_  PVOID               Context,
  _Out_ DXGK_BACKLIGHT_INFO *BacklightInfo
)
{ ... }
````


## -parameters




### -param Context [in]

A handle to a <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> context block that is associated with a display adapter. The display miniport driver's  function previously provided this handle to the DirectX graphics kernel subsystem.


### -param *BacklightInfo [out]

A value of type <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_backlight_info.md">DXGK_BACKLIGHT_INFO</a> that provides the current absolute level of backlight reduction.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



This function is mostly used for debugging and testing purposes to ensure a quality user experience with the display panel. The display miniport driver must always provide accurate information about the integrated display panel when this function is called.

Note that for some hardware a value of zero for <i>BacklightInfo</i>-&gt;<b>BacklightUsersetting</b> or <i>BacklightInfo</i>-&gt;<b>BacklightEffective</b> might not correspond to a Windows brightness level of zero percent. The operating system therefore requires absolute brightness information given by <b>BacklightUsersetting</b> and <b>BacklightEffective</b>. If the hardware uses brightness levels of 0 to 255, it must multiply those values by 256 to correctly map them to the 0 to 65535 range of <b>BacklightUsersetting</b> and <b>BacklightEffective</b>.

This function should be made pageable.

<h3><a id="Computing_backlight_reduction_ratio"></a><a id="computing_backlight_reduction_ratio"></a><a id="COMPUTING_BACKLIGHT_REDUCTION_RATIO"></a>Computing backlight reduction ratio</h3>
The backlight reduction ratio (<i>BRR</i>) is calculated as (<b>BacklightUsersetting</b> - <b>BacklightEffective</b>) / <b>BacklightUsersetting</b>.

The operating system assumes that, in response to a new brightness level request, the driver will boost pixel brightness by a factor of <b>BacklightUsersetting</b> / <b>BacklightEffective</b> = 1.0 / (1.0 - <i>BRR</i>).

As an example, if <i>BRR</i> = 0.2, the driver will typically boost brightness by a factor of 1.0 / (1.0 - <i>BRR</i>) = 1.25, so any pixel with a brightness value above 255 * (1.0 - <i>BRR</i>) = 204 will saturate. Using the value of <i>BacklightInfo</i>-&gt;<b>GammaRamp</b> provided by the driver, the operating system can more accurately estimate the distortion of pixel brightness for a particular image.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_backlight_info.md">DXGK_BACKLIGHT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

