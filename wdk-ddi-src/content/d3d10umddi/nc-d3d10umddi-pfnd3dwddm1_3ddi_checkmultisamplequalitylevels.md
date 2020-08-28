---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS (d3d10umddi.h)
description: Retrieves the number of quality levels that the device supports for the specified number of samples. Supported.
old-location: display\checkmultisamplequalitylevels_d3d11_2_.htm
ms.assetid: A3AD5F2F-4FB9-407C-A436-A0B5F96002D7
ms.date: 05/10/2018
keywords: ["PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function"]
ms.keywords: CheckMultisampleQualityLevels, CheckMultisampleQualityLevels callback function [Display Devices], PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS, PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback, d3d10umddi/CheckMultisampleQualityLevels, display.checkmultisamplequalitylevels_d3d11_2_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
 - d3d10umddi/PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CheckMultisampleQualityLevels
product:
 - Windows
---

# PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function


## -description

 Retrieves the number of quality levels that the device supports for the specified number of samples. Supported

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Format

A value of type <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> that indicates the render-target format that the check is performed for.

### -param SampleCount

The number of samples to retrieve the quality levels for.

### -param Flags

A combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_check_multisample_quality_levels_flag">D3DWDDM1_3DDI_CHECK_MULTISAMPLE_QUALITY_LEVELS_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.

### -param pNumQualityLevels

A pointer to a variable that receives the number of quality levels that the device supports for the specified number of samples.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if the format in the <i>Format</i> parameter does not exist or the <i>pNumQualityLevels</i> parameter is <b>NULL</b>.


If the device does not support multiple sampling with the number of samples that is specified in the <i>SampleCount</i> parameter, the user-mode display driver should return zero in the variable that the <i>pNumQualityLevels</i> parameter points to.

When the driver returns 1 or more in the variable that <i>pNumQualityLevels</i> points to, the driver indicates the number of device-specific sampling variations that are available with the given sample count. For example, if the driver returns 3, quality levels 0, 1, and 2 can be used to create resources with the given sample count. The device manufacturer defines these quality levels, which the Microsoft Direct3D runtime cannot query. However, different quality levels at a fixed sample count might refer to different spatial layouts of the sample locations or different methods of resolving.

If the driver receives 1 in <i>SampleCount</i>, the driver always returns 1 in the variable that <i>pNumQualityLevels</i> points to.

If the driver receives 0 or greater than 32 in <i>SampleCount</i>, the driver always returns 0 in the variable that <i>pNumQualityLevels</i> points to.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels">CheckMultisampleQualityLevels</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm1_3ddi_check_multisample_quality_levels_flag">D3DWDDM1_3DDI_CHECK_MULTISAMPLE_QUALITY_LEVELS_FLAG</a>



<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

