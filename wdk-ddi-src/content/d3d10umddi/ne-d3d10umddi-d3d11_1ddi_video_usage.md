---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_USAGE
title: D3D11_1DDI_VIDEO_USAGE
author: windows-driver-content
description: Identifies how the decode device plays video.
old-location: display\d3d11_1ddi_video_usage.htm
ms.assetid: f107b9a8-d124-4fc3-80b3-dd20a87f9a86
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D11_1DDI_VIDEO_USAGE, D3D11_1DDI_VIDEO_USAGE enumeration [Display Devices], D3D11_1DDI_VIDEO_USAGE_OPTIMAL_QUALITY, D3D11_1DDI_VIDEO_USAGE_OPTIMAL_SPEED, D3D11_1DDI_VIDEO_USAGE_PLAYBACK_NORMAL, d3d10umddi/D3D11_1DDI_VIDEO_USAGE, d3d10umddi/D3D11_1DDI_VIDEO_USAGE_OPTIMAL_QUALITY, d3d10umddi/D3D11_1DDI_VIDEO_USAGE_OPTIMAL_SPEED, d3d10umddi/D3D11_1DDI_VIDEO_USAGE_PLAYBACK_NORMAL, display.d3d11_1ddi_video_usage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D11_1DDI_VIDEO_USAGE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_USAGE
---

# D3D11_1DDI_VIDEO_USAGE enumeration


## -description


Identifies how the decode device plays video.


## -enum-fields




### -field D3D11_1DDI_VIDEO_USAGE_PLAYBACK_NORMAL

Specifies that the device plays video at normal speed.


### -field D3D11_1DDI_VIDEO_USAGE_OPTIMAL_SPEED

Specifies that the device plays video at optimal speed.


### -field D3D11_1DDI_VIDEO_USAGE_OPTIMAL_QUALITY

Specifies that the device plays video at optimal quality.


## -remarks



A value of type <b>D3D11_1DDI_VIDEO_USAGE</b> is specified in the <b>Usage</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450943">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a> structure to help describe a decode device.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450943">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a>
 

 

