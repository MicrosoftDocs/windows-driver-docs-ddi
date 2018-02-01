---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_INPUT
title: D3D11_1DDI_VIDEO_INPUT
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
old-location: display\d3d11_1ddi_video_input.htm
old-project: display
ms.assetid: 371f494c-abd2-43c8-ab06-749144762b01
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_1ddi_video_input, D3D11_1DDI_VIDEO_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_INPUT, D3D11_1DDI_VIDEO_INPUT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_INPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_INPUT
---

# D3D11_1DDI_VIDEO_INPUT structure


## -description


Reserved for system use. Do not use in your driver.


## -syntax


````
typedef struct D3D11_1DDI_VIDEO_INPUT {
  BOOL                        Relocate;
  D3D11_1DDI_VIDEODEVICEFUNCS *p11VideoDeviceFuncs;
} D3D11_1DDI_VIDEO_INPUT;
````


## -struct-fields




### -field Relocate

Reserved for system use. Do not use in your driver.


### -field p11VideoDeviceFuncs

Reserved for system use. Do not use in your driver.

