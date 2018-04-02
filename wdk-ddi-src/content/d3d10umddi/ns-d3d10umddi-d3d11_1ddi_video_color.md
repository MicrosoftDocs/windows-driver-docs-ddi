---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_COLOR
title: D3D11_1DDI_VIDEO_COLOR
author: windows-driver-content
description: Defines a color value for Microsoft Direct3D 11 video.
old-location: display\d3d11_1ddi_video_color.htm
old-project: display
ms.assetid: 200ca1d5-cbfd-4ad8-aa41-8238ea7ea5cf
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_COLOR
---

# D3D11_1DDI_VIDEO_COLOR structure


## -description


Defines a color value for Microsoft Direct3D 11 video.


## -struct-fields






#### - RGBA

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450928">D3D11_1DDI_VIDEO_COLOR_RGBA</a> structure that contains an RGB color value.


#### - YCbCr

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450932">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a> structure that contains a YCbCr color value.


## -remarks



The anonymous union can represent both RGB and YCbCr colors. The interpretation of the union depends on the context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450928">D3D11_1DDI_VIDEO_COLOR_RGBA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450932">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a>
 

 

