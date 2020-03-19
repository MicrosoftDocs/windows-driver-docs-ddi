---
UID: NC:d3dumddi.PFND3DDDI_CREATEVIDEOPROCESSDEVICE
title: PFND3DDDI_CREATEVIDEOPROCESSDEVICE (d3dumddi.h)
description: The CreateVideoProcessDevice function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processing device that is used to process video (for example, to deinterlace the video and adjust ProcAmp properties of the video).
old-location: display\createvideoprocessdevice.htm
tech.root: display
ms.assetid: 3149c7d9-0bf7-4355-8f15-821cf6b92f0a
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATEVIDEOPROCESSDEVICE callback function"]
ms.keywords: CreateVideoProcessDevice, CreateVideoProcessDevice callback function [Display Devices], PFND3DDDI_CREATEVIDEOPROCESSDEVICE, PFND3DDDI_CREATEVIDEOPROCESSDEVICE callback, UserModeDisplayDriver_Functions_2f8b832f-db45-4f76-ab8f-5ba94f818933.xml, d3dumddi/CreateVideoProcessDevice, display.createvideoprocessdevice
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/CreateVideoProcessDevice"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CreateVideoProcessDevice
product:
 - Windows
---

# PFND3DDDI_CREATEVIDEOPROCESSDEVICE callback function

## -description

The <b>CreateVideoProcessDevice</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processing device that is used to process video (for example, to deinterlace the video and adjust ProcAmp properties of the video).

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createvideoprocessdevice">D3DDDIARG_CREATEVIDEOPROCESSDEVICE</a> structure. On input, contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.

## -returns

<b>CreateVideoProcessDevice</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The video processing device is successfully created. | 
| **E_OUTOFMEMORY** | [CreateVideoProcessDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createvideoprocessdevice)  could not allocate the required memory for it to complete. |

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createvideoprocessdevice">D3DDDIARG_CREATEVIDEOPROCESSDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyvideoprocessdevice">DestroyVideoProcessDevice</a>

