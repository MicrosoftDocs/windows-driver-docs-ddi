---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKFORMATSUPPORT
title: PFND3D10DDI_CHECKFORMATSUPPORT
author: windows-driver-content
description: Retrieves the capabilities that the device has with the specified format.
old-location: display\checkformatsupport.htm
old-project: display
ms.assetid: 463ab1e5-08b1-45a1-b7d8-bdfacb3d4bdb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CheckFormatSupport
req.alt-loc: d3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10DDI_CHECKFORMATSUPPORT callback



## -description
Retrieves the capabilities that the device has with the specified format.



## -prototype

````
PFND3D10DDI_CHECKFORMATSUPPORT CheckFormatSupport;

VOID APIENTRY CheckFormatSupport(
  _In_  D3D10DDI_HDEVICE hDevice,
  _In_  DXGI_FORMAT      Format,
  _Out_ UINT             *pFormatCaps
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param Format [in]

 A -typed value of type <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> indicates the pixel format to retrieve capabilities for. 


### -param pFormatCaps [out]

A pointer to a variable that receives a valid bitwise <b>OR</b> of the following values that indicate the capabilities.


### -param D3D10_DDI_FORMAT_SUPPORT_SHADER_SAMPLE (0x00000001)

<dd>
The format can be sampled with any filter in shaders.


### -param D3D10_DDI_FORMAT_SUPPORT_RENDERTARGET (0x00000002)

<dd>
The format can be a render target.


### -param D3D10_DDI_FORMAT_SUPPORT_BLENDABLE (0x00000004)

<dd>
The format is blendable. (You can set this value only if the format can be a render target.)


### -param D3D10_DDI_FORMAT_SUPPORT_MULTISAMPLE_RENDERTARGET (0x00000008)

<dd>
The format can be a render target with a sample count that is greater than one.


### -param D3D10_DDI_FORMAT_SUPPORT_MULTISAMPLE_LOAD (0x00000010)

<dd>
The format can be used for reading individual samples from multiple-sample resources.


### -param D3D10_DDI_FORMAT_SUPPORT_NOT_SUPPORTED (0x80000000)

<dd>
The display device does not support the format at all. This value is currently only valid for the <b>DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM</b>  format. If the driver sets this value, the driver must not set any of the other values.


### -param D3D11_1DDI_FORMAT_SUPPORT_DECODER_OUTPUT (0x00000020)

<dd>
The format can be supported as a decode output resource.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_VIDEO_PROCESSOR_OUTPUT (0x00000040)

<dd>
The format can be a video processor output resource.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_VIDEO_PROCESSOR_INPUT (0x00000080)

<dd>
The format can be a video processor input resource.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_VERTEX_BUFFER (0x00000100)

<dd>
The format can be a vertex buffer.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_UAV_WRITES (0x00000200)

<dd>
The format can be written through an unordered access view (UAV) append buffer.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_BUFFER (0x00000400)

<dd>
The format can be used in a typed Buffer view.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_CAPTURE (0x00000800)

<dd>
The format can be supported as an output to the video capture engine.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_VIDEO_ENCODER (0x00001000)

<dd>
The format can be supported as an input to a hardware-encode Media Foundation Transform (MFT).

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_OUTPUT_MERGER_LOGIC_OP (0x00002000)

<dd>
The format supports shader logic operations.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_SHADER_GATHER (0x00004000)

<dd>
The format supports "Shader gather4" resource attributes.

Available starting with Windows 8.


### -param D3D11_1DDI_FORMAT_SUPPORT_MULTIPLANE_OVERLAY (0x00008000)

<dd>
The format supports multiplane overlays.

Available starting with Windows 8. However, multiplane overlays are supported only in WDDM 1.3 and later drivers, which were introduced with Windows 8.1.


### -param D3DWDDM1_3DDI_FORMAT_SUPPORT_TILED (0x00010000)

<dd>
The format supports use in a tiled resource of type <b>D3D10DDIRESOURCE_TEXTURE1D</b>, <b>D3D10DDIRESOURCE_TEXTURE2D</b>, or <b>D3D10DDIRESOURCE_TEXTURECUBE</b>.

Available starting with Windows 8.1, and supported only by WDDM 1.3 and later drivers.


### -param D3D10_DDI_FORMAT_SUPPORT_NOT_SUPPORTED (0x80000000)

<dd>
The format is not supported at all. This value is valid only for the following formats:

<dl>
<dd><b>DXGI_FORMAT_A8P8</b></dd>
<dd><b>DXGI_FORMAT_AI44</b></dd>
<dd><b>DXGI_FORMAT_AYUV</b></dd>
<dd><b>DXGI_FORMAT_IA44</b></dd>
<dd><b>DXGI_FORMAT_NV11</b></dd>
<dd><b>DXGI_FORMAT_P010

</b></dd>
<dd><b>DXGI_FORMAT_P016</b></dd>
<dd><b>DXGI_FORMAT_P8

</b></dd>
<dd><b>DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM</b></dd>
<dd><b>DXGI_FORMAT_Y210</b></dd>
<dd><b>DXGI_FORMAT_Y216</b></dd>
<dd><b>DXGI_FORMAT_Y410</b></dd>
<dd><b>DXGI_FORMAT_Y416</b></dd>
</dl>
For these formats, only this bit should be set.

Available starting with Windows 8.

</dd>
</dl>

## -returns
None.

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see  Remarks .


## -remarks
The driver can call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function to set <b>E_FAIL</b> if the format in the <i>Format</i> parameter does not exist or can set <b>E_INVALIDARG</b> if the <i>pFormatCaps</i> parameter is <b>NULL</b>. 


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2aef590f-2328-4175-ab60-c72b1fd83db7">DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CHECKFORMATSUPPORT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

