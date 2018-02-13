---
UID: NS:d3d10umddi.D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
title: D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
author: windows-driver-content
description: The D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure describes timestamp-disjoint information that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_TIMESTAMPDISJOINT query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d10_ddi_query_data_timestamp_disjoint.htm
old-project: display
ms.assetid: 1dd7e73d-b804-4018-8c72-732bd68dd8d2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d10_ddi_query_data_timestamp_disjoint, D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure [Display Devices], D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT, UMDisplayDriver_Dx10param_Structs_1dbd9e05-9c61-4753-902c-245471e71e36.xml, d3d10umddi/D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
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
-	D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
---

# D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure


## -description


The D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure describes timestamp-disjoint information that is used in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_TIMESTAMPDISJOINT query type and in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function to return information about the query. 


## -syntax


````
typedef struct D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT {
  UINT64 Frequency;
  BOOL   Disjoint;
} D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT;
````


## -struct-fields




### -field Frequency

The frequency, in Hz, of the timestamp clock. 


### -field Disjoint

A BOOL value that indicates whether something caused the timestamp counter to become discontinuous or disjoint. This value is <b>TRUE</b> if the values from TIMESTAMP queries cannot be guaranteed to be continuous throughout the duration of the D3D10DDI_QUERY_TIMESTAMPDISJOINT query. Otherwise, this value should be <b>FALSE</b>. 


## -remarks



The driver associates a D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure with the D3D10DDI_QUERY_TIMESTAMPDISJOINT query type value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a> enumeration.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

