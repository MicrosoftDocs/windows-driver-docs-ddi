---
UID: NC:d3d10umddi.PFND3D10DDI_SETSHADERRESOURCES
title: PFND3D10DDI_SETSHADERRESOURCES (d3d10umddi.h)
description: The CsSetShaderResources function sets resources for a compute shader.
old-location: display\cssetshaderresources.htm
ms.assetid: 29570c3b-eb3b-4d8f-b471-8f3ea6226e23
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_SETSHADERRESOURCES callback function"]
ms.keywords: CsSetShaderResources, CsSetShaderResources callback function [Display Devices], PFND3D10DDI_SETSHADERRESOURCES, PFND3D10DDI_SETSHADERRESOURCES callback, UserModeDisplayDriverDx11_Functions_0fe556e4-8c6f-4848-b502-d35744c60713.xml, d3d10umddi/CsSetShaderResources, display.cssetshaderresources
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetShaderResources is supported beginning with the Windows 7 operating system.
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
 - "d3d10umddi/CsSetShaderResources"
 - "CsSetShaderResources"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CsSetShaderResources
product:
 - Windows
---

# PFND3D10DDI_SETSHADERRESOURCES callback function

## -description

The <b>CsSetShaderResources</b> function sets resources for a compute shader.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param StartSlot

[in] The offset to the first view to set.

### -param NumViews

The total number of views to set.

### -param Arg4

*phShaderResourceViews* [in]

An array of handles to the shader resource views, beginning at the offset that <i>Offset</i> specifies.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetShaderResources</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The <b>VsSetShaderResources</b> function sets resources for a vertex shader.

The <b>PsSetShaderResources</b> function sets resources for a pixel shader.

The <b>DsSetShaderResources</b> function sets resources for a domain shader.

The <b>GsSetShaderResources</b> function sets resources for a geometry shader.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

