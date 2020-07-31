---
UID: NS:d3d10umddi.D3D11DDI_THREADING_CAPS
title: D3D11DDI_THREADING_CAPS (d3d10umddi.h)
description: The D3D11DDI_THREADING_CAPS structure contains display device threading capabilities.
old-location: display\d3d11ddi_threading_caps.htm
ms.assetid: 11715852-8af2-4ae1-b3a2-c80153ef7cde
ms.date: 05/10/2018
keywords: ["D3D11DDI_THREADING_CAPS structure"]
ms.keywords: D3D11DDI_THREADING_CAPS, D3D11DDI_THREADING_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_0f59187b-c545-4e95-aa28-c2627cb62538.xml, d3d10umddi/D3D11DDI_THREADING_CAPS, display.d3d11ddi_threading_caps
f1_keywords:
 - "d3d10umddi/D3D11DDI_THREADING_CAPS"
 - "D3D11DDI_THREADING_CAPS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11DDI_THREADING_CAPS
targetos: Windows
tech.root: display
req.typenames: D3D11DDI_THREADING_CAPS
---

# D3D11DDI_THREADING_CAPS structure


## -description


The D3D11DDI_THREADING_CAPS structure contains display device threading capabilities. 


## -struct-fields




### -field Caps

[in] A valid bitwise OR of values that describe the threading capabilities of the driver. The Direct3D runtime supports the following values.

|Value|Meaning|
|--- |--- |
|D3D11DDICAPS_FREETHREADED (0x1)|The driver supports free threading.|
|D3D11DDICAPS_COMMANDLISTS (0x2)|This value is deprecated.The driver supports command lists. To support D3D11DDICAPS_COMMANDLISTS, the driver must also support D3D11DDICAPS_FREETHREADED.|
|D3D11DDICAPS_COMMANDLISTS_BUILD_2 (0x4)|The driver supports command lists. To support D3D11DDICAPS_COMMANDLISTS_BUILD_2, the driver must also support D3D11DDICAPS_FREETHREADED.|

 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_2ddicaps_type">D3D10_2DDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>
 

 

