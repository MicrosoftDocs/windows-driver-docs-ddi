---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
title: "_D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD"
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.
old-location: display\d3dddiarg_dxvahd_videoprocessblthd.htm
old-project: display
ms.assetid: 16eb6131-89d5-48da-b5f8-f51b9c37e061
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, UMDisplayDriver_param_Structs_8a72018a-706f-4c26-adca-109365e03ff1.xml, D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure [Display Devices], _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD, display.d3dddiarg_dxvahd_videoprocessblthd
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD
---

# _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure


## -description


The D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure describes a Microsoft DirectX Video Acceleration (VA) video processing high definition operation to perform.


## -syntax


````
typedef struct _D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD {
  HANDLE                      hVideoProcessor;
  DXVAHDDDI_SURFACE           OutputSurface;
  UINT                        OutputFrame;
  UINT                        StreamCount;
  const DXVAHDDDI_STREAM_DATA *pStreams;
} D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD;
````


## -struct-fields




### -field hVideoProcessor

[in] A handle to the DirectX VA video processing device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a> function.


### -field OutputSurface

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_surface.md">DXVAHDDDI_SURFACE</a> structure that describes the output surface to which the video processor composes. 


### -field OutputFrame

[in] A zero-based frame number of the composed output frames. 


### -field StreamCount

[in] The number of streams to process. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field pStreams

[in] An array of <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_data.md">DXVAHDDDI_STREAM_DATA</a> structures that describe the input streams to process. 


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
</ul>If the frame that the <b>OutputFrame</b> member specifies remains unchanged at the next process time, the driver determines that the frame is unchanged (for example, paused) in the entire video processing and composition. Therefore, the driver can use cached data to optimize the frame.

The driver also uses the frame that the <b>OutputFrame</b> member specifies for tagging the command, which the driver submits to the graphics processing unit (GPU).

Input streams are indexed from zero to less than the number that the driver sets in the <b>MaxStreamStates</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a> structure. Each stream has its own stream states associated with the stream index number. The driver processes each stream from zero index and blends on the destination surface one after another. For example, if a video stream is at index zero and a graphics stream is at index one, the driver blends the video stream on the background color and then blends the graphics stream over them.



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_surface.md">DXVAHDDDI_SURFACE</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_data.md">DXVAHDDDI_STREAM_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

