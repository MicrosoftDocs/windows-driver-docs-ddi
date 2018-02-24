---
UID: NC:d3d10umddi.PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT
title: PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT
author: windows-driver-content
description: Queries whether the video processor supports a specified video format.
old-location: display\checkvideoprocessorformat.htm
old-project: display
ms.assetid: f5f18a53-d121-445a-86b7-649624a2f175
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.checkvideoprocessorformat, CheckVideoProcessorFormat callback function [Display Devices], CheckVideoProcessorFormat, PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT, PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT, d3d10umddi/CheckVideoProcessorFormat
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
-	CheckVideoProcessorFormat
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT callback


## -description


Queries whether the video processor supports a specified video format.


## -prototype


````
PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT CheckVideoProcessorFormat;

VOID APIENTRY* CheckVideoProcessorFormat(
  _In_  D3D10DDI_HDEVICE               hDevice,
  _In_  D3D11_1DDI_HVIDEOPROCESSORENUM hVideoProcessorEnum,
  _In_  DXGI_FORMAT                    Format,
  _Out_ UINT                           *pSupported
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSORENUM


### -param DXGI_FORMAT


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessorEnum [in]

A handle to a video processor enumeration object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a> function. 


#### - pSupported [out]

Specifies a bitwise OR of zero or more flags from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_format_support.md">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT</a> enumeration.

For more information, see the Remarks section.


## -returns



This callback function does not return a value.




## -remarks



If the driver can support the format as an input format for the video processor, the driver sets the <b>D3D11_1DDI_VIDEO_FORMAT_SUPPORT_VIDEO_PROCESSOR_INPUT</b> flag in the <i>pSupported</i> parameter.



If the driver can support the format as a video processing render target output format, the driver sets the <b>D3D11_1DDI_VIDEO_FORMAT_SUPPORT_VIDEO_PROCESSOR_OUTPUT</b> flag in the <i>pSupported</i> parameter.



If the driver can support neither, it must set the <i>pSupported</i> parameter to 0.





## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_format_support.md">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

