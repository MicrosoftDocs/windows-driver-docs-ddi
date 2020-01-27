---
UID: NC:d3dumddi.PFND3DDDI_GETOVERLAYCOLORCONTROLS
title: PFND3DDDI_GETOVERLAYCOLORCONTROLS (d3dumddi.h)
description: The GetOverlayColorControls function retrieves color-control settings for the given overlay.
old-location: display\getoverlaycolorcontrols.htm
tech.root: display
ms.assetid: 23b15bb5-4394-406b-8869-f9d1e4e2b539
ms.date: 05/10/2018
ms.keywords: GetOverlayColorControls, GetOverlayColorControls callback function [Display Devices], PFND3DDDI_GETOVERLAYCOLORCONTROLS, PFND3DDDI_GETOVERLAYCOLORCONTROLS callback, UserModeDisplayDriver_Functions_b50c3637-892b-4cc9-ad9a-97feeeb649fc.xml, d3dumddi/GetOverlayColorControls, display.getoverlaycolorcontrols
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: 
f1_keywords:
 - "d3dumddi/GetOverlayColorControls"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - GetOverlayColorControls
product:
 - Windows
---

# PFND3DDDI_GETOVERLAYCOLORCONTROLS callback function

## -description

The <i>GetOverlayColorControls</i> function retrieves color-control settings for the given overlay.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a> structure that describes parameters for retrieving an overlay's color-control settings.

## -returns

<i>GetOverlayColorControls</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The color-control settings were successfully retrieved.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|GetOverlayColorControls could not allocate the required memory for it to complete.|

## -remarks

The Microsoft Direct3D runtime calls the <i>GetOverlayColorControls</i> function to return the current brightness, contrast, hue, saturation, sharpness, gamma, and color-enable settings that are associated with a specific overlay. 

The runtime can also call <i>GetOverlayColorControls</i> for an overlay that is not yet visible. In this situation, when the <b>hOverlay</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a> structure pointed to by <i>pData</i> is set to <b>NULL</b>, the driver should return the default color-control settings of the overlay hardware.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

