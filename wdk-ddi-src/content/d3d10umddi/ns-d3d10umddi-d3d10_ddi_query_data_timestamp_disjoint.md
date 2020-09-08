---
UID: NS:d3d10umddi.D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
title: D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT (d3d10umddi.h)
description: The D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure describes timestamp-disjoint information that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_TIMESTAMPDISJOINT query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d10_ddi_query_data_timestamp_disjoint.htm
ms.assetid: 1dd7e73d-b804-4018-8c72-732bd68dd8d2
ms.date: 05/10/2018
keywords: ["D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure"]
ms.keywords: D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT, D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_1dbd9e05-9c61-4753-902c-245471e71e36.xml, d3d10umddi/D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT, display.d3d10_ddi_query_data_timestamp_disjoint
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
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
f1_keywords:
 - D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
 - d3d10umddi/D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT
---

# D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure


## -description

The D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure describes timestamp-disjoint information that is used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_TIMESTAMPDISJOINT query type and in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a> function to return information about the query.

## -struct-fields

### -field Frequency

The frequency, in Hz, of the timestamp clock.

### -field Disjoint

A BOOL value that indicates whether something caused the timestamp counter to become discontinuous or disjoint. This value is <b>TRUE</b> if the values from TIMESTAMP queries cannot be guaranteed to be continuous throughout the duration of the D3D10DDI_QUERY_TIMESTAMPDISJOINT query. Otherwise, this value should be <b>FALSE</b>.

## -remarks

The driver associates a D3D10_DDI_QUERY_DATA_TIMESTAMP_DISJOINT structure with the D3D10DDI_QUERY_TIMESTAMPDISJOINT query type value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a> enumeration.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a>

