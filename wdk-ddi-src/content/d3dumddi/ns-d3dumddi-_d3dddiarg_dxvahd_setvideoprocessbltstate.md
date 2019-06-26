---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE
title: _D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE (d3dumddi.h)
description: The D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure describes the bit-block transfer (bitblt) state of the video processor to change and the data that is used to change the state.
old-location: display\d3dddiarg_dxvahd_setvideoprocessbltstate.htm
tech.root: display
ms.assetid: ebcd58d7-f0b3-43ea-b08f-f0c2618902d7
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE, D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure [Display Devices], UMDisplayDriver_param_Structs_fd02ddf9-535d-4c4b-a6fe-6c765170e6f9.xml, _D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE, d3dumddi/D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE, display.d3dddiarg_dxvahd_setvideoprocessbltstate
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE is supported beginning with the Windows 7 operating system.
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
- D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE
---

# _D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure


## -description


The D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE structure describes the bit-block transfer (bitblt) state of the video processor to change and the data that is used to change the state. 


## -struct-fields




### -field hVideoProcessor

[in] A handle to the video processor whose bitblt state is changed.


### -field State

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-_dxvahdddi_blt_state">DXVAHDDDI_BLT_STATE</a>-typed value that indicates the type of bitblt to set.


### -field DataSize

[in] The size, in bytes, of the data that is used to change the bitblt state.


### -field pData

[in] A pointer to the data that is used to change the bitblt state. For more information about the types of data that <b>pData</b> can point to, see the values of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-_dxvahdddi_blt_state">DXVAHDDDI_BLT_STATE</a> enumeration. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-_dxvahdddi_blt_state">DXVAHDDDI_BLT_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate">SetVideoProcessBltState</a>
 

 

