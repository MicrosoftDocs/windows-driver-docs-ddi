---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS (d3d10umddi.h)
description: Retrieves the number of quality levels that the device supports for the specified number of samples. Supported.
old-location: display\checkmultisamplequalitylevels_d3d11_2_.htm
ms.date: 01/10/2022
keywords: ["PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function"]
ms.keywords: CheckMultisampleQualityLevels, CheckMultisampleQualityLevels callback function [Display Devices], PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS, PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback, d3d10umddi/CheckMultisampleQualityLevels, display.checkmultisamplequalitylevels_d3d11_2_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1 (WDDM 1.3)
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
 - PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
product:
 - Windows
---

# PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function

## -description

 **PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS** retrieves the number of quality levels that the device supports for the specified number of samples.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Format

A value of type [**DXGI_FORMAT**](/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) that indicates the render-target format that the check is performed for.

### -param SampleCount

The number of samples to retrieve the quality levels for.

### -param Flags

A combination of [**D3DWDDM1_3DDI_CHECK_MULTISAMPLE_QUALITY_LEVELS_FLAG**](ne-d3d10umddi-d3dwddm1_3ddi_check_multisample_quality_levels_flag.md) values that are combined by using a bitwise OR operation.

### -param pNumQualityLevels

A pointer to a variable that receives the number of quality levels that the device supports for the specified number of samples.

## -remarks

The driver can use the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) callback function to set an error code. The driver can set **E_INVALIDARG** if the format in the **Format** parameter does not exist or the **pNumQualityLevels** parameter is NULL.

If the device does not support multiple sampling with the number of samples that is specified in the **SampleCount** parameter, the user-mode display driver should return zero in the variable that the **pNumQualityLevels** parameter points to.

When the driver returns 1 or more in the variable that **pNumQualityLevels** points to, the driver indicates the number of device-specific sampling variations that are available with the given sample count. For example, if the driver returns 3, quality levels 0, 1, and 2 can be used to create resources with the given sample count. The device manufacturer defines these quality levels, which the Microsoft Direct3D runtime cannot query. However, different quality levels at a fixed sample count might refer to different spatial layouts of the sample locations or different methods of resolving.

If the driver receives 1 in **SampleCount**, the driver always returns 1 in the variable that **pNumQualityLevels** points to.

If the driver receives 0 or greater than 32 in **SampleCount**, the driver always returns 0 in the variable that **pNumQualityLevels** points to.

## -see-also

[**CheckMultisampleQualityLevels**](nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md)

[**D3DWDDM1_3DDI_CHECK_MULTISAMPLE_QUALITY_LEVELS_FLAG**](ne-d3d10umddi-d3dwddm1_3ddi_check_multisample_quality_levels_flag.md)

[**DXGI_FORMAT**](/win32/api/dxgiformat/ne-dxgiformat-dxgi_format)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
