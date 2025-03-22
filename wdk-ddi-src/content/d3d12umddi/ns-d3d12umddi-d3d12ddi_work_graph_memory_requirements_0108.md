---
UID: NS:d3d12umddi.D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
tech.root: display
title: D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
f1_keywords:
 - D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
 - d3d12umddi/D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
---

# D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108 structure (d3d12umddi.h)

## -description

**D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108** is the structure in which the user-mode driver's [**pfnGetWorkGraphMemoryRequirements**](nc-d3d12umddi-pfnd3d12ddi_get_work_graph_memory_requirements_0108.md) function returns work graph memory requirements.

## -struct-fields

### -field MinSizeInBytes

[out] The minimum number of bytes the driver needs for backing memory.

### -field MaxSizeInBytes

[out] The maximum number of bytes the driver needs for backing memory.

### -field SizeGranularityInBytes

[out] Multiple to use to determine other sizes that the driver can use. Sizes that are larger than **MinSizeInBytes** are larger by a multiple of **SizeGranularityInBytes**. The application can provide sizes for backing memory that are larger than **MinSizeInBytes** plus an integer multiple of **SizeGranularityInBytes**, or larger than **MaxSizeInBytes**, but it simply wastes memory as the driver won't touch memory beyond the size range and granularity specifications here.

## -remarks

The minimum can be reported as zero if the system doesn't need any backing memory for the graph. If the minimum is reported as zero, the maximum might also be reported as zero unless the system can use backing store if the app wants but can also handle being given none. When zero is reported as a valid size, application can pass null for the backing memory in SetProgram().

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108**](nc-d3d12umddi-pfnd3d12ddi_get_work_graph_memory_requirements_0108.md)
