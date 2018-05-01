---
UID: NS:d3d10umddi.D3D11DDI_THREADING_CAPS
title: D3D11DDI_THREADING_CAPS
author: windows-driver-content
description: The D3D11DDI_THREADING_CAPS structure contains display device threading capabilities.
old-location: display\d3d11ddi_threading_caps.htm
old-project: display
ms.assetid: 11715852-8af2-4ae1-b3a2-c80153ef7cde
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D11DDI_THREADING_CAPS, D3D11DDI_THREADING_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_0f59187b-c545-4e95-aa28-c2627cb62538.xml, d3d10umddi/D3D11DDI_THREADING_CAPS, display.d3d11ddi_threading_caps
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D11DDI_THREADING_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11DDI_THREADING_CAPS
---

# D3D11DDI_THREADING_CAPS structure


## -description


The D3D11DDI_THREADING_CAPS structure contains display device threading capabilities. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541894">D3D10_2DDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>
 

 

