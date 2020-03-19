---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_POSSIBLE
title: DXGK_BRIGHTNESS_GET_POSSIBLE (dispmprt.h)
description: The DxgkDdiGetPossibleBrightness function retrieves the brightness levels that an integrated display panel supports.
old-location: display\dxgkddigetpossiblebrightness.htm
tech.root: display
ms.assetid: aed565f5-a9c1-4130-a192-68bb699b4bd1
ms.date: 05/10/2018
keywords: ["DXGK_BRIGHTNESS_GET_POSSIBLE callback function"]
ms.keywords: DXGK_BRIGHTNESS_GET_POSSIBLE, DXGK_BRIGHTNESS_GET_POSSIBLE callback, DmFunctions_b14a6b62-e156-4548-9a0d-0a256cf84069.xml, DxgkDdiGetPossibleBrightness, DxgkDdiGetPossibleBrightness callback function [Display Devices], display.dxgkddigetpossiblebrightness, dispmprt/DxgkDdiGetPossibleBrightness
f1_keywords:
 - "dispmprt/DxgkDdiGetPossibleBrightness"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
- dispmprt.h
api_name:
- DxgkDdiGetPossibleBrightness
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGK_BRIGHTNESS_GET_POSSIBLE callback function


## -description


The <i>DxgkDdiGetPossibleBrightness</i> function retrieves the brightness levels that an integrated display panel supports.


## -parameters




### -param Context [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param BufferSize [in]

[in] The size, in bytes, of the buffer that is passed in the <i>BrightnessLevels</i> parameter. 


### -param LevelCount [out]

[out] A pointer to a variable that receives the number of brightness levels that the driver returns in the buffer that the <i>BrightnessLevels</i> parameter points to. 


### -param BrightnessLevels [out]

[in/out] A pointer to a buffer that receives the brightness levels that an integrated display panel supports.


## -returns



<i>DxgkDdiGetPossibleBrightness</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. 




## -remarks



The display miniport driver should return brightness levels in the buffer that the <i>BrightnessLevels</i> parameter points to in the following order:

<ul>
<li>
The first brightness level value is the brightness level that the BIOS uses when the computer runs on AC power. 

</li>
<li>
The second brightness level value is the brightness level that the BIOS uses when the computer runs on DC power. 

</li>
<li>
The remaining brightness level values are hardware-supported brightness levels. 

</li>
</ul>
To simplify your job of implementing a display miniport driver, the operating system provides the driver with the buffer that the <i>BrightnessLevels</i> parameter points to.

<i>DxgkDdiGetPossibleBrightness</i> should be made pageable. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

