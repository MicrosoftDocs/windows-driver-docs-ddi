---
UID: NS:d3d10umddi.D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
title: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS (d3d10umddi.h)
description: The D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d11_ddi_query_data_pipeline_statistics.htm
ms.date: 05/10/2018
keywords: ["D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure"]
ms.keywords: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS, D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_68a59a1f-0f02-4be2-b417-5c4064df23fb.xml, d3d10umddi/D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS, display.d3d11_ddi_query_data_pipeline_statistics
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS is supported beginning with the Windows 7 operating system.
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
targetos: Windows
tech.root: display
req.typenames: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
f1_keywords:
 - D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
 - d3d10umddi/D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
---

# D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure


## -description

The D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a> function to return information about the query.

## -struct-fields

### -field IAVertices

The number of input assembler (IA) veritces.

### -field IAPrimitives

The number of IA primitives.

### -field VSInvocations

The number of vertex shader (VS) invocations.

### -field GSInvocations

The number of geometry shader (GS) invocations.

### -field GSPrimitives

The number of GS primitives.

### -field CInvocations

The number of clipper invocations.

### -field CPrimitives

The number of clipper primitives.

### -field PSInvocations

The number of pixel shader (PS) invocations.

### -field HSInvocations

The number of hull shader (HS) invocations.

### -field DSInvocations

The number of domain shader (DS) invocations.

### -field CSInvocations

The number of compute shader (CS) invocations.

## -remarks

The driver associates a D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure with the D3D11DDI_QUERY_PIPELINESTATS query type value from the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a> enumeration.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a>
