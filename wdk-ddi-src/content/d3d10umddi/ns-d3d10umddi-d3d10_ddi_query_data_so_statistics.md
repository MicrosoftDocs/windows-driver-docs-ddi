---
UID: NS:d3d10umddi.D3D10_DDI_QUERY_DATA_SO_STATISTICS
title: D3D10_DDI_QUERY_DATA_SO_STATISTICS
author: windows-driver-content
description: The D3D10_DDI_QUERY_DATA_SO_STATISTICS structure describes stream output statistics that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_STREAMOUTPUTSTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d10_ddi_query_data_so_statistics.htm
old-project: display
ms.assetid: 641c8f8d-e398-4ca4-9e28-bba2ef7d1bd3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_Dx10param_Structs_3748a5db-9ce8-4763-baac-4110b754188d.xml, D3D10_DDI_QUERY_DATA_SO_STATISTICS structure [Display Devices], display.d3d10_ddi_query_data_so_statistics, D3D10_DDI_QUERY_DATA_SO_STATISTICS, d3d10umddi/D3D10_DDI_QUERY_DATA_SO_STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDI_QUERY_DATA_SO_STATISTICS
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_QUERY_DATA_SO_STATISTICS
---

# D3D10_DDI_QUERY_DATA_SO_STATISTICS structure


## -description


The D3D10_DDI_QUERY_DATA_SO_STATISTICS structure describes stream output statistics that is used in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_STREAMOUTPUTSTATS 

query type and in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function to return information about the query. 


## -syntax


````
typedef struct D3D10_DDI_QUERY_DATA_SO_STATISTICS {
  UINT64 NumPrimitivesWritten;
  UINT64 PrimitivesStorageNeeded;
} D3D10_DDI_QUERY_DATA_SO_STATISTICS;
````


## -struct-fields




### -field NumPrimitivesWritten

The number of primitives that is written to the stream output resource. 


### -field PrimitivesStorageNeeded

The number of primitives that would have been written to the stream output resource if the resource was big enough. 


## -remarks



The driver associates a D3D10_DDI_QUERY_DATA_SO_STATISTICS structure with the D3D10DDI_QUERY_STREAMOUTPUTSTATS query type value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a> enumeration.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_QUERY_DATA_SO_STATISTICS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

