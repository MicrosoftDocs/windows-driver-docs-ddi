---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION
title: DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION (dispmprt.h)
description: Retrieves the current level of backlight reduction that is applied to the integrated display panel.
old-location: display\dxgkddigetbacklightreduction.htm
tech.root: display
ms.assetid: 018cb4a0-e71d-407e-8fe9-716312099b73
ms.date: 05/10/2018
keywords: ["DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback function"]
ms.keywords: DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION, DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback, DxgkDdiGetBacklightReduction, DxgkDdiGetBacklightReduction callback function [Display Devices], display.dxgkddigetbacklightreduction, dispmprt/DxgkDdiGetBacklightReduction
f1_keywords:
 - "dispmprt/DxgkDdiGetBacklightReduction"
 - "DxgkDdiGetBacklightReduction"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Dispmprt.h
api_name:
- DxgkDdiGetBacklightReduction
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback function


## -description


Retrieves the current level of backlight reduction that is applied to the integrated display panel.


## -parameters




### -param Context [in]

A handle to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> context block that is associated with a display adapter. The display miniport driver's  function previously provided this handle to the DirectX graphics kernel subsystem.


### -param BacklightInfo [out]

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_backlight_info">DXGK_BACKLIGHT_INFO</a> that provides the current absolute level of backlight reduction.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



This function is mostly used for debugging and testing purposes to ensure a quality user experience with the display panel. The display miniport driver must always provide accurate information about the integrated display panel when this function is called.

Note that for some hardware a value of zero for <i>BacklightInfo</i>-><b>BacklightUsersetting</b> or <i>BacklightInfo</i>-><b>BacklightEffective</b> might not correspond to a Windows brightness level of zero percent. The operating system therefore requires absolute brightness information given by <b>BacklightUsersetting</b> and <b>BacklightEffective</b>. If the hardware uses brightness levels of 0 to 255, it must multiply those values by 256 to correctly map them to the 0 to 65535 range of <b>BacklightUsersetting</b> and <b>BacklightEffective</b>.

This function should be made pageable.

<h3><a id="Computing_backlight_reduction_ratio"></a><a id="computing_backlight_reduction_ratio"></a><a id="COMPUTING_BACKLIGHT_REDUCTION_RATIO"></a>Computing backlight reduction ratio</h3>
The backlight reduction ratio (<i>BRR</i>) is calculated as (<b>BacklightUsersetting</b> - <b>BacklightEffective</b>) / <b>BacklightUsersetting</b>.

The operating system assumes that, in response to a new brightness level request, the driver will boost pixel brightness by a factor of <b>BacklightUsersetting</b> / <b>BacklightEffective</b> = 1.0 / (1.0 - <i>BRR</i>).

As an example, if <i>BRR</i> = 0.2, the driver will typically boost brightness by a factor of 1.0 / (1.0 - <i>BRR</i>) = 1.25, so any pixel with a brightness value above 255 * (1.0 - <i>BRR</i>) = 204 will saturate. Using the value of <i>BacklightInfo</i>-><b>GammaRamp</b> provided by the driver, the operating system can more accurately estimate the distortion of pixel brightness for a particular image.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_backlight_info">DXGK_BACKLIGHT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

