---
UID: NC:d3d10umddi.PFND3D11_1DDI_SETCONSTANTBUFFERS
title: PFND3D11_1DDI_SETCONSTANTBUFFERS (d3d10umddi.h)
description: Sets constant buffers for a compute shader.
old-location: display\cssetconstantbuffers_d3d11_1_.htm
ms.assetid: 6A2B50BF-415D-47BB-9514-B15F717A76EA
ms.date: 10/12/2018
keywords: ["PFND3D11_1DDI_SETCONSTANTBUFFERS callback function"]
ms.keywords: CsSetConstantBuffers(D3D11_1), CsSetConstantBuffers(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_SETCONSTANTBUFFERS, PFND3D11_1DDI_SETCONSTANTBUFFERS callback, d3d10umddi/CsSetConstantBuffers(D3D11_1), display.cssetconstantbuffers_d3d11_1_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CsSetConstantBuffers(D3D11_1)"
 - "CsSetConstantBuffers(D3D11_1)"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CsSetConstantBuffers(D3D11_1)
product:
 - Windows
---

# PFND3D11_1DDI_SETCONSTANTBUFFERS callback function

## -description

Sets constant buffers for a compute shader.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param StartSlot

[in] The starting constant buffer to set.

### -param NumBuffers

The total number of buffers to set.

### -param Arg4

*phBuffers* [in]

An array of handles to the constant buffers, beginning with the buffer that <i>StartBuffer</i> specifies.

### -param pFirstConstant

A pointer to the first constant in the buffer pointed to by <i>StartBuffer</i>.

### -param pNumConstants

The number of constants in the  buffer pointed to by  <i>StartBuffer</i>.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

Buffers that this function specifies are created with the D3D10_BIND_CONSTANT_BUFFER flag. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of this function (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The <b>VsSetConstantBuffers</b> function sets constant buffers for a vertex shader.

The <b>GsSetConstantBuffers</b> function sets constant buffers for a geometry shader.

The <b>HsSetConstantBuffers</b> function sets constant buffers for a hull shader.

The <b>PsSetConstantBuffers</b> function sets constant buffers for a pixel shader.

The <b>DsSetConstantBuffers</b> function sets constant buffers for a domain shader.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

