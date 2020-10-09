---
UID: NC:d3d10umddi.PFND3D10DDI_SETTEXTFILTERSIZE
title: PFND3D10DDI_SETTEXTFILTERSIZE (d3d10umddi.h)
description: The SetTextFilterSize function sets the width and height of the monochrome convolution filter.
old-location: display\settextfiltersize.htm
ms.assetid: 663fd3c3-7a8f-446d-b45a-392716116407
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_SETTEXTFILTERSIZE callback function"]
ms.keywords: PFND3D10DDI_SETTEXTFILTERSIZE, PFND3D10DDI_SETTEXTFILTERSIZE callback, SetTextFilterSize, SetTextFilterSize callback function [Display Devices], UserModeDisplayDriverDx10_Functions_418992fe-bd22-446c-94a2-2a4d23fd63a7.xml, d3d10umddi/SetTextFilterSize, display.settextfiltersize
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
 - PFND3D10DDI_SETTEXTFILTERSIZE
 - d3d10umddi/PFND3D10DDI_SETTEXTFILTERSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - SetTextFilterSize
---

# PFND3D10DDI_SETTEXTFILTERSIZE callback function


## -description

The <i>SetTextFilterSize</i> function sets the width and height of the monochrome convolution filter.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*Width* [in]

The width of the monochrome convolution filter. The width can be from 1 to 7 texels.

### -param Arg3

*Height* [in]

The height of the monochrome convolution filter. The height can be from 1 to 7 texels.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The number of samples that are required from a kernel's dimensions is actually (<i>Width</i> + 1) x (<i>Height</i> + 1), which can come out to from 4 to 64 samples. These settings apply across all samplers that are configured to use the D3D10_DDI_FILTER_TEXT_1BIT filter from the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_filter">D3D10_DDI_FILTER</a> enumeration.

<i>SetTextFilterSize</i> ensures that values that are supplied in the <i>Width</i> and <i>Height</i> parameters are in range. The default vaules for <i>Width</i> and <i>Height</i> are both 1, initially. The driver must set these default values during device creation.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED. However, if device removal interfered with the operation of <i>SetTextFilterSize</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_filter">D3D10_DDI_FILTER</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>