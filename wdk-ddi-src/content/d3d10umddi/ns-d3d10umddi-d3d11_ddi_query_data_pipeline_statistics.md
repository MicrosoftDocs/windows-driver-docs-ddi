---
UID: NS:d3d10umddi.D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
title: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
author: windows-driver-content
description: The D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d11_ddi_query_data_pipeline_statistics.htm
old-project: display
ms.assetid: d82b4e91-6734-4644-811d-fb64cfb9f5c4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS, D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_68a59a1f-0f02-4be2-b417-5c4064df23fb.xml, d3d10umddi/D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS, display.d3d11_ddi_query_data_pipeline_statistics
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS
---

# D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure


## -description


The D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function to return information about the query. 


## -syntax


````
typedef struct D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS {
  UINT64 IAVertices;
  UINT64 IAPrimitives;
  UINT64 VSInvocations;
  UINT64 GSInvocations;
  UINT64 GSPrimitives;
  UINT64 CInvocations;
  UINT64 CPrimitives;
  UINT64 PSInvocations;
  UINT64 HSInvocations;
  UINT64 DSInvocations;
  UINT64 CSInvocations;
} D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS;
````


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



The driver associates a D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure with the D3D11DDI_QUERY_PIPELINESTATS query type value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a> enumeration.




## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

