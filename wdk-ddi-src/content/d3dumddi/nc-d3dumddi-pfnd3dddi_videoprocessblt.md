---
UID: NC:d3dumddi.PFND3DDDI_VIDEOPROCESSBLT
title: PFND3DDDI_VIDEOPROCESSBLT (d3dumddi.h)
description: The VideoProcessBlt function processes a video frame by using the specified Microsoft DirectX Video Accelerator (VA) video processing device.
old-location: display\videoprocessblt.htm
tech.root: display
ms.assetid: 719465dd-4547-491c-ab30-ae63bba1b72c
ms.date: 05/10/2018
keywords: ["PFND3DDDI_VIDEOPROCESSBLT callback function"]
ms.keywords: PFND3DDDI_VIDEOPROCESSBLT, PFND3DDDI_VIDEOPROCESSBLT callback, UserModeDisplayDriver_Functions_23e47fd3-a838-4b56-82c3-7894d2b173a1.xml, VideoProcessBlt, VideoProcessBlt callback function [Display Devices], d3dumddi/VideoProcessBlt, display.videoprocessblt
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/VideoProcessBlt"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - VideoProcessBlt
product:
 - Windows
---

# PFND3DDDI_VIDEOPROCESSBLT callback function

## -description

The <i>VideoProcessBlt</i> function processes a video frame by using the specified Microsoft DirectX Video Accelerator (VA) video processing device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_videoprocessblt">D3DDDIARG_VIDEOPROCESSBLT</a> structure that describes the DirectX VA video processing operation to perform.

## -returns

<i>VideoProcessBlt</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The DirectX VA video processing operation is successfully performed. | 
| **E_OUTOFMEMORY** | VideoProcessBlt could not allocate the required memory for it to complete. |

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_videoprocessblt">D3DDDIARG_VIDEOPROCESSBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

