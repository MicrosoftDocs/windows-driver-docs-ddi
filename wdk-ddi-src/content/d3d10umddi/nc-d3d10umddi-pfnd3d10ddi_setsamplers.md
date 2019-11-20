---
UID: NC:d3d10umddi.PFND3D10DDI_SETSAMPLERS
title: PFND3D10DDI_SETSAMPLERS (d3d10umddi.h)
description: The CsSetSamplers function sets samplers for a compute shader.
old-location: display\cssetsamplers.htm
ms.assetid: 7bf05fb6-e959-464a-9e6b-74c568d1d88c
ms.date: 05/10/2018
ms.keywords: CsSetSamplers, CsSetSamplers callback function [Display Devices], PFND3D10DDI_SETSAMPLERS, PFND3D10DDI_SETSAMPLERS callback, UserModeDisplayDriverDx11_Functions_a2d1c287-1dab-4852-a643-8d568d04f64d.xml, d3d10umddi/CsSetSamplers, display.cssetsamplers
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetSamplers is supported beginning with the Windows 7 operating system.
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
 - "d3d10umddi/CsSetSamplers"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CsSetSamplers
product:
 - Windows
---

# PFND3D10DDI_SETSAMPLERS callback function

## -description

The <b>CsSetSamplers</b> function sets samplers for a compute shader.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param StartSlot

*Offset* [in]

The offset to the first sampler to set.

### -param NumSamplers

[in] The total number of samplers to set.

### -param Arg4

*phSamplers* [in]

An array of handles to the samplers, beginning at the offset that <i>Offset</i> specifies.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetSamplers</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The HsSetSamplers function sets samplers for a hull shader.

The GsSetSamplers function sets samplers for a geometry shader.

The VsSetSamplers function sets samplers for a vertex shader.

The PsSetSamplers function sets samplers for a pixel shader.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

