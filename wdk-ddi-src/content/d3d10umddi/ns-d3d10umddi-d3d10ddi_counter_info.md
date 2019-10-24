---
UID: NS:d3d10umddi.D3D10DDI_COUNTER_INFO
title: D3D10DDI_COUNTER_INFO (d3d10umddi.h)
description: The D3D10DDI_COUNTER_INFO structure describes information to manipulate counters.
old-location: display\d3d10ddi_counter_info.htm
ms.assetid: fda3d4a2-4c1a-454d-bcb0-4174699c5bb8
ms.date: 05/10/2018
ms.keywords: D3D10DDI_COUNTER_INFO, D3D10DDI_COUNTER_INFO structure [Display Devices], UMDisplayDriver_Dx10param_Structs_7a4f801d-7954-4c1a-af86-1482281732cb.xml, d3d10umddi/D3D10DDI_COUNTER_INFO, display.d3d10ddi_counter_info
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10DDI_COUNTER_INFO"
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
- D3D10DDI_COUNTER_INFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_COUNTER_INFO
---

# D3D10DDI_COUNTER_INFO structure


## -description


The D3D10DDI_COUNTER_INFO structure describes information to manipulate counters.


## -struct-fields




### -field LastDeviceDependentCounter

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a>-typed value that identifies the largest device-dependent counter identifier that the device supports. If none are supported, the user-mode display driver must set the value to 0; otherwise, the driver sets the value to greater than or equal to D3D10DDI_COUNTER_DEVICE_DEPENDENT_0 (0x40000000). 


### -field NumSimultaneousCounters

[out] The number of simultaneously active counters that the driver supports. 


### -field NumDetectableParallelUnits

[out] The number of detectable parallel units that the counters can identify. Valid values are from 1 through 4.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo">CheckCounterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a>
 

 

