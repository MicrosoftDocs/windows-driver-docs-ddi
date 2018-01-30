---
UID: NS:d3d10umddi.D3D11DDI_THREADING_CAPS
title: D3D11DDI_THREADING_CAPS
author: windows-driver-content
description: The D3D11DDI_THREADING_CAPS structure contains display device threading capabilities.
old-location: display\d3d11ddi_threading_caps.htm
old-project: display
ms.assetid: 11715852-8af2-4ae1-b3a2-c80153ef7cde
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11DDI_THREADING_CAPS, display.d3d11ddi_threading_caps, D3D11DDI_THREADING_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_0f59187b-c545-4e95-aa28-c2627cb62538.xml, D3D11DDI_THREADING_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_THREADING_CAPS is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
apiname:
-	D3D11DDI_THREADING_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11DDI_THREADING_CAPS
---

# D3D11DDI_THREADING_CAPS structure


## -description


The D3D11DDI_THREADING_CAPS structure contains display device threading capabilities. 


## -syntax


````
typedef struct D3D11DDI_THREADING_CAPS {
  UINT Caps;
} D3D11DDI_THREADING_CAPS;
````


## -struct-fields




### -field Caps

[in] A valid bitwise OR of values that describe the threading capabilities of the driver. The Direct3D runtime supports the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D11DDICAPS_FREETHREADED (0x1)

</td>
<td>
The driver supports free threading.

</td>
</tr>
<tr>
<td>
D3D11DDICAPS_COMMANDLISTS (0x2)

</td>
<td>
This value is deprecated.The driver supports command lists. To support D3D11DDICAPS_COMMANDLISTS, the driver must also support D3D11DDICAPS_FREETHREADED.

</td>
</tr>
<tr>
<td>
D3D11DDICAPS_COMMANDLISTS_BUILD_2 (0x4)

</td>
<td>
The driver supports command lists. To support D3D11DDICAPS_COMMANDLISTS_BUILD_2, the driver must also support D3D11DDICAPS_FREETHREADED. 

</td>
</tr>
</table> 


## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_2ddicaps_type.md">D3D10_2DDICAPS_TYPE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDI_THREADING_CAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

