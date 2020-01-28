---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR
title: _D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR (d3dumddi.h)
description: The D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processor to create.
old-location: display\d3dddiarg_dxvahd_createvideoprocessor.htm
tech.root: display
ms.assetid: fafb1b1f-409d-4eab-a5dd-22fd1ab830d2
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR, D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure [Display Devices], UMDisplayDriver_param_Structs_c2d925e2-646c-46dc-9795-1a885aa64a02.xml, _D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR, d3dumddi/D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR, display.d3dddiarg_dxvahd_createvideoprocessor
f1_keywords:
 - "d3dumddi/D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR is supported beginning with the Windows 7 operating system.
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
- D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR
---

# _D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure


## -description


The D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processor to create. 


## -struct-fields




### -field pVPGuid

[in] A pointer to the GUID that represents a DirectX VA video processor to create. The Microsoft Direct3D runtime can call the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to query (D3DDDICAPS_DXVAHD_GETVPCAPS) for the capabilities of the video processors that the driver supports. Each <b>VPGuid</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a> structure in the array that the driver's <b>GetCaps</b> returns specifies a video processor that the driver supports.  


### -field hVideoProcessor

[out] A handle to the video processor. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the video processor in subsequent calls. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a>
 

 

