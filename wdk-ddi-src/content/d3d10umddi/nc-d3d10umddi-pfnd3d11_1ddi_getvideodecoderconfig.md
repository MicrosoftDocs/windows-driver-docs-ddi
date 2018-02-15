---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERCONFIG
title: PFND3D11_1DDI_GETVIDEODECODERCONFIG
author: windows-driver-content
description: Queries the video decoder configuration for a specified video operation.
old-location: display\getvideodecoderconfig.htm
old-project: display
ms.assetid: e13cb42b-258e-4fa6-8dc0-8983b118af3c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.getvideodecoderconfig, pfnGetVideoDecoderConfig callback function [Display Devices], pfnGetVideoDecoderConfig, PFND3D11_1DDI_GETVIDEODECODERCONFIG, PFND3D11_1DDI_GETVIDEODECODERCONFIG, d3d10umddi/pfnGetVideoDecoderConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnGetVideoDecoderConfig
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_GETVIDEODECODERCONFIG callback


## -description


Queries the video decoder configuration for a specified video operation.


## -prototype


````
PFND3D11_1DDI_GETVIDEODECODERCONFIG pfnGetVideoDecoderConfig;

VOID APIENTRY* pfnGetVideoDecoderConfig(
  _In_        D3D10DDI_HDEVICE                hDevice,
  _In_  const D3D11_1DDI_VIDEO_DECODER_DESC   *pDecodeDesc,
  _In_        UINT                            Index,
  _Out_       D3D11_1DDI_VIDEO_DECODER_CONFIG *pConfig
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








### -param UINT


#### - Index [in]

The zero-based index of the video decoder configuration that is used for the specified operation. The display miniport driver specifies the maximum number of video decoder configurations that are required for the operation through a call to its <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount.md">GetVideoDecoderConfigCount</a> function.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - pConfig [out]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure that describes the video decoder configuration.


#### - pDecodeDesc [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.


## -returns



This callback function does not return a value.




## -remarks



The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i> and <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderConfig</b> function.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount.md">GetVideoDecoderConfigCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETVIDEODECODERCONFIG callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

