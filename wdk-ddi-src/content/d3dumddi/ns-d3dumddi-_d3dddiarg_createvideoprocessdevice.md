---
UID: NS:d3dumddi._D3DDDIARG_CREATEVIDEOPROCESSDEVICE
title: _D3DDDIARG_CREATEVIDEOPROCESSDEVICE (d3dumddi.h)
description: The D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processing device to create.
old-location: display\d3dddiarg_createvideoprocessdevice.htm
tech.root: display
ms.assetid: b875755c-9559-41ee-8a9b-1de05a2f1dab
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CREATEVIDEOPROCESSDEVICE, D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure [Display Devices], UMDisplayDriver_param_Structs_b8b0d8fa-b750-440d-afa4-556ffb33074a.xml, _D3DDDIARG_CREATEVIDEOPROCESSDEVICE, d3dumddi/D3DDDIARG_CREATEVIDEOPROCESSDEVICE, display.d3dddiarg_createvideoprocessdevice
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_CREATEVIDEOPROCESSDEVICE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEVIDEOPROCESSDEVICE
---

# _D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure


## -description


The D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processing device to create. 


## -struct-fields




### -field pVideoProcGuid

[in] A pointer to the GUID that represents a DirectX VA video processing device to create. The Microsoft Direct3D runtime can call the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to query for the video processing GUIDs that the driver supports. 


### -field VideoDesc

[in] The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a> structure for the video stream that the video processing device should process.


### -field RenderTargetFormat

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


### -field MaxSubStreams

[in] The maximum number of video substreams that can be sent to the video processing device. If this value is set to zero, the device never receives any video substreams.


### -field hVideoProcess

[in/out] A handle to the video processing device. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the video processing device in subsequent calls.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createvideoprocessdevice">CreateVideoProcessDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>
 

 

