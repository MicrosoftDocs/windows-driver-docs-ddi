---
UID: NS:d3dumddi._D3DDDIARG_VIDEOPROCESSENDFRAME
title: "_D3DDDIARG_VIDEOPROCESSENDFRAME"
author: windows-driver-content
description: The D3DDDIARG_VIDEOPROCESSENDFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) video process that should stop processing a frame.
old-location: display\d3dddiarg_videoprocessendframe.htm
old-project: display
ms.assetid: 948f10cb-215c-4a21-a275-ffdbf0ee1593
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_VIDEOPROCESSENDFRAME, D3DDDIARG_VIDEOPROCESSENDFRAME structure [Display Devices], UMDisplayDriver_param_Structs_16fccea8-3a26-4470-bf7d-a94b04f01797.xml, _D3DDDIARG_VIDEOPROCESSENDFRAME, d3dumddi/D3DDDIARG_VIDEOPROCESSENDFRAME, display.d3dddiarg_videoprocessendframe
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_VIDEOPROCESSENDFRAME
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_VIDEOPROCESSENDFRAME
---

# _D3DDDIARG_VIDEOPROCESSENDFRAME structure


## -description


The D3DDDIARG_VIDEOPROCESSENDFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) video process that should stop processing a frame. 


## -struct-fields




### -field hVideoProcess

A handle to the DirectX VA video process device. The user-mode display driver returns this handle in a call to its <a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a> function.


### -field pHandleComplete

This member is reserved and should be set to <b>NULL</b>. 


## -see-also




<a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a>



<a href="https://msdn.microsoft.com/a5be6834-bb27-4da0-8802-25a9ca58c101">VideoProcessEndFrame</a>
 

 

