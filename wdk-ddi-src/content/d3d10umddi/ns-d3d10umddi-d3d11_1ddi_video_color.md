---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_COLOR
title: D3D11_1DDI_VIDEO_COLOR
author: windows-driver-content
description: Defines a color value for Microsoft Direct3D 11 video.
old-location: display\d3d11_1ddi_video_color.htm
old-project: display
ms.assetid: 200ca1d5-cbfd-4ad8-aa41-8238ea7ea5cf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_VIDEO_COLOR, D3D11_1DDI_VIDEO_COLOR structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_COLOR, display.d3d11_1ddi_video_color
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_COLOR
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_COLOR
---

# D3D11_1DDI_VIDEO_COLOR structure


## -description


Defines a color value for Microsoft Direct3D 11 video.


## -struct-fields






#### - YCbCr

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450932">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a> structure that contains a YCbCr color value.


#### - RGBA

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450928">D3D11_1DDI_VIDEO_COLOR_RGBA</a> structure that contains an RGB color value.


## -remarks



The anonymous union can represent both RGB and YCbCr colors. The interpretation of the union depends on the context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450928">D3D11_1DDI_VIDEO_COLOR_RGBA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450932">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_COLOR structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

