---
UID: NS:d3dhal._DD_GETD3DQUERYDATA
title: _DD_GETD3DQUERYDATA (d3dhal.h)
description: DirectX 9.0 and later versions only. DD_GETD3DQUERYDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERY.
old-location: display\dd_getd3dquerydata.htm
tech.root: display
ms.assetid: a3bacd56-c25a-45d1-bd9f-b19bc1f95c8f
ms.date: 05/10/2018
ms.keywords: DD_GETD3DQUERYDATA, DD_GETD3DQUERYDATA structure [Display Devices], _DD_GETD3DQUERYDATA, d3dhal/DD_GETD3DQUERYDATA, d3dstrct_ec5ab755-9f1e-4add-bcf1-73bcb01988e6.xml, display.dd_getd3dquerydata
f1_keywords:
 - "d3dhal/DD_GETD3DQUERYDATA"
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- d3dhal.h
api_name:
- DD_GETD3DQUERYDATA
product:
- Windows
targetos: Windows
req.typenames: DD_GETD3DQUERYDATA
---

# _DD_GETD3DQUERYDATA structure


## -description



   DirectX 9.0 and later versions only.
   

DD_GETD3DQUERYDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERY.


## -struct-fields




### -field gdi2

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwQueryIndex

Specifies the index of the query type to return.


### -field QueryType

Receives a value from the D3DQUERYTYPE enumeration that specifies the actual query capability.


## -remarks



The runtime identifies the query type to be returned with an integer index whose value varies between zero and one less than the number of supported query types that were reported earlier by the driver in a D3DGDI2_TYPE_GETD3DQUERYCOUNT query. How these indices are mapped to actual query types is left to the driver. However, each index must map uniquely to one supported query type. The order in which the query types are reported is not significant. 

When processing this <b>GetDriverInfo2</b> request the driver should read the value in the union as if it were the <b>dwQueryIndex</b> member and map that value to one of the supported query types (probably by using the value in <b>dwQueryIndex</b> as an index into an array of D3DQUERYTYPE values). The driver should then copy that query type into the union as if it were the <b>QueryType</b> member. The runtime guarantees that it only passes an index to the driver that is in the range zero to one less than the number of query types reported by the driver. The range of the index should be validated in the debug driver build.

For more information about D3DQUERYTYPE, see the DirectX SDK documentation.




## -see-also




D3DDP2OP_CREATEQUERY



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getd3dquerycountdata">DD_GETD3DQUERYCOUNTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>
 

 

