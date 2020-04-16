---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS (d3d10umddi.h)
description: The CheckMultisampleQualityLevels function retrieves the number of quality levels that the device supports for the specified number of samples.
old-location: display\checkmultisamplequalitylevels.htm
ms.assetid: 2b6a0ab8-f197-48c3-baf2-305b77b7e8b5
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function"]
ms.keywords: CheckMultisampleQualityLevels, CheckMultisampleQualityLevels callback function [Display Devices], PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS, PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback, UserModeDisplayDriverDx10_Functions_d19bc4c0-49ba-4e1c-b19e-667905ceb391.xml, d3d10umddi/CheckMultisampleQualityLevels, display.checkmultisamplequalitylevels
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CheckMultisampleQualityLevels"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CheckMultisampleQualityLevels
product:
 - Windows
---

# PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function

## -description

The <b>CheckMultisampleQualityLevels</b> function retrieves the number of quality levels that the device supports for the specified number of samples.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*Format* [in]

A DXGI_FORMAT-typed value that indicates the render-target format that the check is performed for.

### -param Arg3

*SampleCount* [in]

The number of samples to retrieve the quality levels for.

### -param Arg4

*pNumQualityLevels* [out]

A pointer to a variable that receives the number of quality levels that the device supports for the specified number of samples.

## -remarks


The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. The driver can set E_INVALIDARG if the format in the <i>Format</i> parameter does not exist or the <i>pNumQualityLevels</i> parameter is <b>NULL</b>.


If the device does not support multiple sampling with the number of samples that is specified in the <i>SampleCount</i> parameter, the user-mode display driver should return 0 in the variable that the <i>pNumQualityLevels</i> parameter points to.

When the driver returns 1 or more in the variable that <i>pNumQualityLevels</i> points to, the driver indicates the number of device-specific sampling variations that are available with the given sample count. For example, if the driver returns 3, quality levels 0, 1, and 2 can be used to create resources with the given sample count. The device manufacturer defines these quality levels, which the Microsoft Direct3D runtime cannot query. However, different quality levels at a fixed sample count might refer to different spatial layouts of the sample locations or different methods of resolving.

If the driver receives 1 in <i>SampleCount</i>, the driver always returns 1 in the variable that <i>pNumQualityLevels</i> points to.

If the driver receives 0 or greater than 32 in <i>SampleCount</i>, the driver always returns 0 in the variable that <i>pNumQualityLevels</i> points to.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

