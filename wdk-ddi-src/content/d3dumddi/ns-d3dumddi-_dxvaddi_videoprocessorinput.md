---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSORINPUT
title: "_DXVADDI_VIDEOPROCESSORINPUT"
author: windows-driver-content
description: The DXVADDI_VIDEOPROCESSORINPUT structure describes a video stream that is processed by a video processing device type.
old-location: display\dxvaddi_videoprocessorinput.htm
old-project: display
ms.assetid: 539d32a5-4566-4b8e-b9de-da8d5be3c2f2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA2_Structs_87cc7918-2fb5-4b73-a62c-ab9a3817c154.xml, _DXVADDI_VIDEOPROCESSORINPUT, display.dxvaddi_videoprocessorinput, d3dumddi/DXVADDI_VIDEOPROCESSORINPUT, DXVADDI_VIDEOPROCESSORINPUT, DXVADDI_VIDEOPROCESSORINPUT structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVADDI_VIDEOPROCESSORINPUT
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOPROCESSORINPUT
---

# _DXVADDI_VIDEOPROCESSORINPUT structure


## -description


The DXVADDI_VIDEOPROCESSORINPUT structure describes a video stream that is processed by a video processing device type.


## -syntax


````
typedef struct _DXVADDI_VIDEOPROCESSORINPUT {
  const GUID        *pVideoProcGuid;
  DXVADDI_VIDEODESC VideoDesc;
  D3DDDIFORMAT      RenderTargetFormat;
} DXVADDI_VIDEOPROCESSORINPUT;
````


## -struct-fields




### -field pVideoProcGuid

[in] A pointer to a GUID that represents the video processing device type. 


### -field VideoDesc

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a> structure that describes the video stream. 


### -field RenderTargetFormat

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


## -remarks


When the D3DDDICAPS_GETVIDEOPROCESSORRTFORMATCOUNT, D3DDDICAPS_GETVIDEOPROCESSORRTFORMATS, D3DDDICAPS_GETVIDEOPROCESSORRTSUBSTREAMFORMATCOUNT, or D3DDDICAPS_GETVIDEOPROCESSORRTSUBSTREAMFORMATS <a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>-type value is sent in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function, the driver ignores the <b>RenderTargetFormat</b> member of DXVADDI_VIDEOPROCESSORINPUT.



## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videoprocessorcaps.md">DXVADDI_VIDEOPROCESSORCAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOPROCESSORINPUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

