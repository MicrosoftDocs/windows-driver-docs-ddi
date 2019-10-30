---
UID: NE:d3d10umddi.D3D10_DDI_MAP_FLAG
title: D3D10_DDI_MAP_FLAG (d3d10umddi.h)
description: The D3D10_DDI_MAP_FLAG enumeration type contains flags that identify how to map to a subresource in a call to the driver's ResourceMap function.
old-location: display\d3d10_ddi_map_flag.htm
ms.assetid: e17ca347-6514-47df-9373-5d33fc7f8e5c
ms.date: 05/10/2018
ms.keywords: D3D10_DDI_MAP_FLAG, D3D10_DDI_MAP_FLAG enumeration [Display Devices], D3D10_DDI_MAP_FLAG_DONOTWAIT, D3D10_DDI_MAP_FLAG_MASK, UMDisplayDriver_Dx10param_Structs_ff1e6692-48bb-4381-831a-3d090bbb6f3f.xml, d3d10umddi/D3D10_DDI_MAP_FLAG, d3d10umddi/D3D10_DDI_MAP_FLAG_DONOTWAIT, d3d10umddi/D3D10_DDI_MAP_FLAG_MASK, display.d3d10_ddi_map_flag
ms.topic: enum
f1_keywords:
 - "d3d10umddi/D3D10_DDI_MAP_FLAG"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10_DDI_MAP_FLAG
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_MAP_FLAG
---

# D3D10_DDI_MAP_FLAG enumeration


## -description


The D3D10_DDI_MAP_FLAG enumeration type contains flags that identify how to map to a subresource in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function.


## -enum-fields




### -field D3D10_DDI_MAP_FLAG_DONOTWAIT

The driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function to set the ERR_WASSTILLDRAWING error code if contention exists between an application and hardware when the driver receives the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>.


### -field D3D10_DDI_MAP_FLAG_MASK

A mask value that indicates the valid bitfields in a bitwise OR combination of the values from this enumeration. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

