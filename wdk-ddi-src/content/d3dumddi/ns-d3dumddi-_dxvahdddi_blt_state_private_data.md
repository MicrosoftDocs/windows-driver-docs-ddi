---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_PRIVATE_DATA
title: "_DXVAHDDDI_BLT_STATE_PRIVATE_DATA"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_PRIVATE_DATA structure describes data that specifies the private bit-block transfer (bitblt) state.
old-location: display\dxvahdddi_blt_state_private_data.htm
old-project: display
ms.assetid: f9c0f137-e84c-4626-aa6a-dce352bf7bb0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXVA2_Structs_162bb87d-6383-4c29-b137-0316ace07a65.xml, DXVAHDDDI_BLT_STATE_PRIVATE_DATA, DXVAHDDDI_BLT_STATE_PRIVATE_DATA structure [Display Devices], _DXVAHDDDI_BLT_STATE_PRIVATE_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_PRIVATE_DATA, display.dxvahdddi_blt_state_private_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_PRIVATE_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_BLT_STATE_PRIVATE_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_PRIVATE_DATA
---

# _DXVAHDDDI_BLT_STATE_PRIVATE_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_PRIVATE_DATA structure describes data that specifies the private bit-block transfer (bitblt) state. 


## -struct-fields




### -field Guid

[in] A GUID that identifies the private bitblt state.  


### -field DataSize

[in] The size, in bytes, of the private bitblt state data. 


### -field pData

[in/out] A pointer to the private bitblt state data. The caller sets <b>pData</b> to <b>NULL</b> to retrieve the size of the private bitblt state data. 


## -remarks



Unlike other bitblt states (<a href="https://msdn.microsoft.com/library/windows/hardware/ff562978">DXVAHDDDI_BLT_STATE</a>), the Direct3D runtime does not maintain the private bitblt state. An application and the driver communicate the private bitblt state directly in a proprietary manner, which consists of setting and retrieving the private bitblt state. To set private bitblt state, the application causes the Direct3D runtime to specify the DXVAHDDDI_BLT_STATE_PRIVATE state in the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a> function. To retrieve private bitblt state, the application causes the Direct3D runtime to call the driver's <a href="https://msdn.microsoft.com/bb4c04cf-0125-47bf-8fc8-88d807e7b6ad">GetVideoProcessBltStatePrivate</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562978">DXVAHDDDI_BLT_STATE</a>



<a href="https://msdn.microsoft.com/bb4c04cf-0125-47bf-8fc8-88d807e7b6ad">GetVideoProcessBltStatePrivate</a>



<a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a>
 

 

