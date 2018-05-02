---
UID: NS:d3dumddi._D3DDDIARG_SETLIGHT
title: "_D3DDDIARG_SETLIGHT"
author: windows-driver-content
description: The D3DDDIARG_SETLIGHT structure describes how to set light properties.
old-location: display\d3dddiarg_setlight.htm
old-project: display
ms.assetid: 91da1c7a-aff5-4ece-b18d-14bd41e95464
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_SETLIGHT, D3DDDIARG_SETLIGHT structure [Display Devices], UMDisplayDriver_param_Structs_85eaa308-4edf-44ee-9235-e8637c10aa35.xml, _D3DDDIARG_SETLIGHT, d3dumddi/D3DDDIARG_SETLIGHT, display.d3dddiarg_setlight
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_SETLIGHT
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETLIGHT
---

# _D3DDDIARG_SETLIGHT structure


## -description


The D3DDDIARG_SETLIGHT structure describes how to set light properties. 


## -struct-fields




### -field Index

[in] An index into an array of lights.


### -field DataType

[in] A valid bitwise OR of the following flags that indicate the type of light data:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDISETLIGHT_DATA

</td>
<td>
Specifies that a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544579">D3DDDI_LIGHT</a> structure that defines light properties is supplied in the <i>pLightProperties</i> parameter in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/28e3992e-a636-47e2-a5a6-5da06d276b5c">SetLight</a> function.

</td>
</tr>
<tr>
<td>
D3DDDISETLIGHT_ENABLE

</td>
<td>
Enables the light whose index is specified in the <b>Index</b> member.

</td>
</tr>
<tr>
<td>
D3DDDISETLIGHT_DISABLE

</td>
<td>
Disables the light whose index is specified in <b>Index</b>

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544579">D3DDDI_LIGHT</a>



<a href="https://msdn.microsoft.com/28e3992e-a636-47e2-a5a6-5da06d276b5c">SetLight</a>
 

 

