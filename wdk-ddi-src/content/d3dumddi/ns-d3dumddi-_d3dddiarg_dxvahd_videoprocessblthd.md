---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
title: "_D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD"
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.
old-location: display\d3dddiarg_dxvahd_videoprocessblthd.htm
old-project: display
ms.assetid: 16eb6131-89d5-48da-b5f8-f51b9c37e061
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure [Display Devices], UMDisplayDriver_param_Structs_8a72018a-706f-4c26-adca-109365e03ff1.xml, _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, d3dumddi/D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, display.d3dddiarg_dxvahd_videoprocessblthd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
---

# _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure


## -description


The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.


## -struct-fields




### -field hVideoProcessor

[in] A handle to the DirectX VA video processing device. The user-mode display driver returns this handle in a call to its <a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a> function.


### -field OutputSurface

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563106">DXVAHDDDI_SURFACE</a> structure that describes the output surface to which the video processor composes. 


### -field OutputFrame

[in] A zero-based frame number of the composed output frames. 


### -field StreamCount

[in] The number of streams to process. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field pStreams

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a> structures that describe the input streams to process. 


## -remarks



The output surface that the <b>OutputSurface</b> member specifies, which must be one of the following surface types:

<ul>
<li>
A video surface that is created with the DXVAHD_SURFACE_TYPE_VIDEO_OUTPUT type. 

</li>
<li>
A render target surface or a surface that is created with D3DUSAGE_RENDERTARGET usage. 

</li>
<li>
A swap chain. 

</li>
<li>
A swap chain with overlay swap effect. 

</li>
</ul>
If the frame that the <b>OutputFrame</b> member specifies remains unchanged at the next process time, the driver determines that the frame is unchanged (for example, paused) in the entire video processing and composition. Therefore, the driver can use cached data to optimize the frame.

The driver also uses the frame that the <b>OutputFrame</b> member specifies for tagging the command, which the driver submits to the graphics processing unit (GPU).

Input streams are indexed from zero to less than the number that the driver sets in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. Each stream has its own stream states associated with the stream index number. The driver processes each stream from zero index and blends on the destination surface one after another. For example, if a video stream is at index zero and a graphics stream is at index one, the driver blends the video stream on the background color and then blends the graphics stream over them.




## -see-also




<a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563106">DXVAHDDDI_SURFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>
 

 

