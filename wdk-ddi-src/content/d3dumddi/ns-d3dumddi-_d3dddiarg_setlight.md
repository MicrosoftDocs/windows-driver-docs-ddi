---
UID: NS:d3dumddi._D3DDDIARG_SETLIGHT
title: "_D3DDDIARG_SETLIGHT"
author: windows-driver-content
description: The D3DDDIARG_SETLIGHT structure describes how to set light properties.
old-location: display\d3dddiarg_setlight.htm
old-project: display
ms.assetid: 91da1c7a-aff5-4ece-b18d-14bd41e95464
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_SETLIGHT, _D3DDDIARG_SETLIGHT, display.d3dddiarg_setlight, d3dumddi/D3DDDIARG_SETLIGHT, D3DDDIARG_SETLIGHT structure [Display Devices], UMDisplayDriver_param_Structs_85eaa308-4edf-44ee-9235-e8637c10aa35.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_SETLIGHT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETLIGHT
---

# _D3DDDIARG_SETLIGHT structure


## -description


The D3DDDIARG_SETLIGHT structure describes how to set light properties. 


## -syntax


````
typedef struct _D3DDDIARG_SETLIGHT {
  UINT                 Index;
  D3DDDI_SETLIGHT_TYPE DataType;
} D3DDDIARG_SETLIGHT;
````


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
Specifies that a pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_light.md">D3DDDI_LIGHT</a> structure that defines light properties is supplied in the <i>pLightProperties</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setlight.md">SetLight</a> function.

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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setlight.md">SetLight</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_light.md">D3DDDI_LIGHT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETLIGHT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

