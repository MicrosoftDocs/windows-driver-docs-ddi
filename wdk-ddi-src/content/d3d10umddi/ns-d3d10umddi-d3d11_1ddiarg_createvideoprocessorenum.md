---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
title: D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
author: windows-driver-content
description: Specifies the attributes of a video processor enumeration object.
old-location: display\d3d11_1ddiarg_createvideoprocessorenum.htm
old-project: display
ms.assetid: 7edcd852-429f-4059-92bb-99c7874a9357
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM, D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM, display.d3d11_1ddiarg_createvideoprocessorenum
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
-	D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM structure


## -description


Specifies the attributes of a video processor enumeration object.


## -syntax


````
typedef struct D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM {
  D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC Desc;
} D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM;
````


## -struct-fields




### -field Desc

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_content_desc.md">D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC</a> structure that describes a video stream for a video processor.


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_content_desc.md">D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC</a>



 

 


