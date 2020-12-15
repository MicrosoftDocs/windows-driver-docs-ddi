---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKFORMATSUPPORT
title: PFND3D10DDI_CHECKFORMATSUPPORT (d3d10umddi.h)
description: Retrieves the capabilities that the device has with the specified format.
old-location: display\checkformatsupport.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CHECKFORMATSUPPORT callback function"]
ms.keywords: CheckFormatSupport, CheckFormatSupport callback function [Display Devices], D3D10_DDI_FORMAT_SUPPORT_BLENDABLE, D3D10_DDI_FORMAT_SUPPORT_MULTISAMPLE_LOAD, D3D10_DDI_FORMAT_SUPPORT_MULTISAMPLE_RENDERTARGET, D3D10_DDI_FORMAT_SUPPORT_NOT_SUPPORTED, D3D10_DDI_FORMAT_SUPPORT_RENDERTARGET, D3D10_DDI_FORMAT_SUPPORT_SHADER_SAMPLE, D3D11_1DDI_FORMAT_SUPPORT_BUFFER, D3D11_1DDI_FORMAT_SUPPORT_CAPTURE, D3D11_1DDI_FORMAT_SUPPORT_DECODER_OUTPUT, D3D11_1DDI_FORMAT_SUPPORT_MULTIPLANE_OVERLAY, D3D11_1DDI_FORMAT_SUPPORT_OUTPUT_MERGER_LOGIC_OP, D3D11_1DDI_FORMAT_SUPPORT_SHADER_GATHER, D3D11_1DDI_FORMAT_SUPPORT_UAV_WRITES, D3D11_1DDI_FORMAT_SUPPORT_VERTEX_BUFFER, D3D11_1DDI_FORMAT_SUPPORT_VIDEO_ENCODER, D3D11_1DDI_FORMAT_SUPPORT_VIDEO_PROCESSOR_INPUT, D3D11_1DDI_FORMAT_SUPPORT_VIDEO_PROCESSOR_OUTPUT, D3DWDDM1_3DDI_FORMAT_SUPPORT_TILED, PFND3D10DDI_CHECKFORMATSUPPORT, PFND3D10DDI_CHECKFORMATSUPPORT callback, UserModeDisplayDriverDx10_Functions_4b619814-6ced-4177-a158-5311acb99f6d.xml, d3d10umddi/CheckFormatSupport, display.checkformatsupport
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
 - PFND3D10DDI_CHECKFORMATSUPPORT
 - d3d10umddi/PFND3D10DDI_CHECKFORMATSUPPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CheckFormatSupport
product:
 - Windows
---

# PFND3D10DDI_CHECKFORMATSUPPORT callback function


## -description

Retrieves the capabilities that the device has with the specified format.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*Format* [in]

A [DXGI_FORMAT](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) typed value that indicates the pixel format to retrieve capabilities for.

### -param Arg3

*pFormatCaps* [out]

A pointer to a variable that receives a valid bitwise <b>OR</b> of the following values that indicate the capabilities.

| Value | Description |
|:---|:---|
|D3D10_DDI_FORMAT_SUPPORT_SHADER_SAMPLE (0x00000001)|The format can be sampled with any filter in shaders.|
|D3D10_DDI_FORMAT_SUPPORT_RENDERTARGET (0x00000002)|The format can be a render target.|
|D3D10_DDI_FORMAT_SUPPORT_BLENDABLE (0x00000004)|The format is blendable. (You can set this value only if the format can be a render target.)|
|D3D10_DDI_FORMAT_SUPPORT_MULTISAMPLE_RENDERTARGET (0x00000008)|The format can be a render target with a sample count that is greater than one.|
|D3D10_DDI_FORMAT_SUPPORT_MULTISAMPLE_LOAD (0x00000010)|The format can be used for reading individual samples from multiple-sample resources.|
|D3D10_DDI_FORMAT_SUPPORT_NOT_SUPPORTED (0x80000000)|The display device does not support the format at all. This value is currently only valid for the <b>DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM</b>  format. If the driver sets this value, the driver must not set any of the other values.<br/>The format is not supported at all. This value is valid only for the following formats:<br/><br/><b>DXGI_FORMAT_A8P8</b><br/><b>DXGI_FORMAT_AI44</b><br/><b>DXGI_FORMAT_AYUV</b><br/><b>DXGI_FORMAT_IA44</b><br/><b>DXGI_FORMAT_NV11</b><br/><b>DXGI_FORMAT_P010</b><br/><b>DXGI_FORMAT_P016</b><br/><b>DXGI_FORMAT_P8</b><br/><b>DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM</b><br/><b>DXGI_FORMAT_Y210</b><br/><b>DXGI_FORMAT_Y216</b><br/><b>DXGI_FORMAT_Y410</b><br/><b>DXGI_FORMAT_Y416</b><br/><br/>For these formats, only this bit should be set.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_DECODER_OUTPUT (0x00000020)|The format can be supported as a decode output resource.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_VIDEO_PROCESSOR_OUTPUT (0x00000040)|The format can be a video processor output resource.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_VIDEO_PROCESSOR_INPUT (0x00000080)|The format can be a video processor input resource.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_VERTEX_BUFFER (0x00000100)|The format can be a vertex buffer.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_UAV_WRITES (0x00000200)|The format can be written through an unordered access view (UAV) append buffer.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_BUFFER (0x00000400)|The format can be used in a typed Buffer view.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_CAPTURE (0x00000800)|The format can be supported as an output to the video capture engine.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_VIDEO_ENCODER (0x00001000)|The format can be supported as an input to a hardware-encode Media Foundation Transform (MFT).<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_OUTPUT_MERGER_LOGIC_OP (0x00002000)|The format supports shader logic operations.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_SHADER_GATHER (0x00004000)|The format supports "Shader gather4" resource attributes.<br/>Available starting with Windows 8.|
|D3D11_1DDI_FORMAT_SUPPORT_MULTIPLANE_OVERLAY (0x00008000)|The format supports multiplane overlays.<br/>Available starting with Windows 8. However, multiplane overlays are supported only in WDDM 1.3 and later drivers, which were introduced with Windows 8.1.|
|D3DWDDM1_3DDI_FORMAT_SUPPORT_TILED (0x00010000)|The format supports use in a tiled resource of type <b>D3D10DDIRESOURCE_TEXTURE1D</b>, <b>D3D10DDIRESOURCE_TEXTURE2D</b>, or <b>D3D10DDIRESOURCE_TEXTURECUBE</b>.<br/>Available starting with Windows 8.1, and supported only by WDDM 1.3 and later drivers.|

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 


The driver can call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function to set <b>E_FAIL</b> if the format in the <i>Format</i> parameter does not exist or can set <b>E_INVALIDARG</b> if the <i>pFormatCaps</i> parameter is <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>



<a href="/windows-hardware/drivers/display/dxgi-format-r10g10b10-xr-bias-a2-unorm">DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
