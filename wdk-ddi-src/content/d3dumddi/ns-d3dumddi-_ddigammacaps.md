---
UID: NS:d3dumddi._DDIGAMMACAPS
title: "_DDIGAMMACAPS"
author: windows-driver-content
description: The DDIGAMMACAPS structure describes gamma-ramp capabilities that the user-mode display driver supports.
old-location: display\ddigammacaps.htm
old-project: display
ms.assetid: 4db605f8-a1ed-4b75-8c72-f4846ae7007e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D_other_Structs_7aa0b131-f7e5-4208-b3bb-7a35fa0d5ef1.xml, DDIGAMMACAPS, DDIGAMMACAPS structure [Display Devices], _DDIGAMMACAPS, d3dumddi/DDIGAMMACAPS, display.ddigammacaps
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
-	DDIGAMMACAPS
product: Windows
targetos: Windows
req.typenames: DDIGAMMACAPS
---

# _DDIGAMMACAPS structure


## -description


The DDIGAMMACAPS structure describes gamma-ramp capabilities that the user-mode display driver supports.


## -syntax


````
typedef struct _DDIGAMMACAPS {
  UINT GammaCaps;
} DDIGAMMACAPS;
````


## -struct-fields




### -field GammaCaps

[out] A valid bitwise OR of the following capability bits that the driver supports.

<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
GAMMA_CAP_RGB256x3x16 (0x00000001)

</td>
<td>
Gamma-ramp data is stored as 256 16-bit RGB values.

</td>
</tr>
</table>
 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDIGAMMACAPS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

