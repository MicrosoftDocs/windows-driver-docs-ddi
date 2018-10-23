---
UID: NS:d3d10umddi.D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
title: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
author: windows-driver-content
description: The D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d11_ddi_query_data_pipeline_statistics.htm
ms.assetid: d82b4e91-6734-4644-811d-fb64cfb9f5c4
ms.date: 05/10/2018
ms.keywords: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS, D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_68a59a1f-0f02-4be2-b417-5c4064df23fb.xml, d3d10umddi/D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS, display.d3d11_ddi_query_data_pipeline_statistics
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
---

# D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure


## -description


The D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the <a href="https://msdn.microsoft.com/abe6a82f-1613-4c74-9e81-01939db74bfd">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the <a href="https://msdn.microsoft.com/78ee9813-e23e-4d46-acc4-f2fa88559b03">QueryGetData</a> function to return information about the query. 


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

The number of commute shader (CS) invocations. 


## -remarks



The driver associates a D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure with the D3D11DDI_QUERY_PIPELINESTATS query type value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a> enumeration.




## -see-also




<a href="https://msdn.microsoft.com/abe6a82f-1613-4c74-9e81-01939db74bfd">CreateQuery(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>



<a href="https://msdn.microsoft.com/78ee9813-e23e-4d46-acc4-f2fa88559b03">QueryGetData</a>
 

 

