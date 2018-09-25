---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
title: "_D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE"
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure describes the stream state of the video processor to change and the data that is used to change the state.
old-location: display\d3dddiarg_dxvahd_setvideoprocessstreamstate.htm
tech.root: display
ms.assetid: f1f99725-4110-49b4-9149-1f6d03faeb0e
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure [Display Devices], UMDisplayDriver_param_Structs_6b11ff68-267b-47f0-aa04-17d3eea71e20.xml, _D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, d3dumddi/D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, display.d3dddiarg_dxvahd_setvideoprocessstreamstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
---

# _D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure


## -description


The D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE structure describes the stream state of the video processor to change and the data that is used to change the state. 


## -struct-fields




### -field hVideoProcessor

[in] A handle to the video processor whose stream state is changed.


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field State

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563068">DXVAHDDDI_STREAM_STATE</a>-typed value that indicates the stream state to modify.


### -field DataSize

[in] The size, in bytes, of the data that is used to change the stream state.


### -field pData

[in] A pointer to the data that is used to change the stream state. For more information about the types of data that <b>pData</b> can point to, see the values of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563068">DXVAHDDDI_STREAM_STATE</a> enumeration. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563068">DXVAHDDDI_STREAM_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/b48fbe58-056a-4c3b-8e1e-c65515c21ee4">SetVideoProcessStreamState</a>
 

 

