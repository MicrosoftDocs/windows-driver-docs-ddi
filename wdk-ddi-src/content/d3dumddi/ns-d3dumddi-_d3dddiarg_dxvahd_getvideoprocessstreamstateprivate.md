---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
title: _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE (d3dumddi.h)
description: The D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure describes the private stream-state of the video processor to retrieve.
old-location: display\d3dddiarg_dxvahd_getvideoprocessstreamstateprivate.htm
tech.root: display
ms.assetid: f55dc37a-fb67-48fe-8e32-29b2e71b6abc
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure"]
ms.keywords: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure [Display Devices], UMDisplayDriver_param_Structs_5c255d85-4e9e-4a3f-a782-3fd96dbcd0d9.xml, _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, d3dumddi/D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, display.d3dddiarg_dxvahd_getvideoprocessstreamstateprivate
f1_keywords:
 - "d3dumddi/D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE"
 - "D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE is supported beginning with the Windows 7 operating system.
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
- D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
---

# _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure


## -description


The D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure describes the private stream-state of the video processor to retrieve. 


## -struct-fields




### -field hVideoProcessor

[in] A handle to the video processor whose private stream-state is the runtime requests.


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field pData

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure that identifies the private stream state to retrieve. The driver uses DXVAHDDDI_STREAM_STATE_PRIVATE_DATA to return the private stream-state data. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate">GetVideoProcessStreamStatePrivate</a>
 

 

