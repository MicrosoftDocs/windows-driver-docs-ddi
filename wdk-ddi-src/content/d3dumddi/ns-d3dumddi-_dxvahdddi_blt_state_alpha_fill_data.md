---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
title: "_DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure describes data that specifies the alpha-fill mode of the output.
old-location: display\dxvahdddi_blt_state_alpha_fill_data.htm
tech.root: display
ms.assetid: 67fb316e-359f-4bf0-b061-a4b18e359f38
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA2_Structs_0b64fc90-1ad4-4d38-9fda-68454167b9dd.xml, DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA, DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure [Display Devices], _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA, display.dxvahdddi_blt_state_alpha_fill_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
---

# _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure describes data that specifies the alpha-fill mode of the output. 


## -struct-fields




### -field Mode

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562974">DXVAHDDDI_ALPHA_FILL_MODE</a>-typed value that indicates the type of alpha-fill mode to set. The default value is DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, which indicates to fill the output with the alpha value of the background color. 


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number, which the driver sets in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. The driver should refer to this number only when the <b>Mode</b> member is set to DXVAHD_ALPHA_FILL_MODE_SOURCE_STREAM. The default value is zero. 


## -remarks



The Direct3D runtime specifies the DXVAHDDDI_BLT_STATE_ALPHA_FILL state in the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a> function only when the output format is a format type with alpha (for example, D3DDDIFMT_A8R8G8B8 from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration).

The DXVAHD_ALPHA_FILL_MODE_SOURCE_STREAM mode requires the following conditions:

<ul>
<li>
The DXVAHDDDI_BLT_STATE_ALPHA_FILL state only affects alpha within the destination rectangle. The rest of the output remains unchanged. 

</li>
<li>
If the input format type is without alpha, the source alpha is considered as opaque. 

</li>
<li>
If the input stream is disabled or unavailable, the output remains unchanged. 

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562974">DXVAHDDDI_ALPHA_FILL_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/6796372c-279d-427c-a2a4-9b7c99494f53">SetVideoProcessBltState</a>
 

 

