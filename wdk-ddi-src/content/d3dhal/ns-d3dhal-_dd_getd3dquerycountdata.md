---
UID: NS:d3dhal._DD_GETD3DQUERYCOUNTDATA
title: _DD_GETD3DQUERYCOUNTDATA (d3dhal.h)
description: DirectX 9.0 and later versions only. DD_GETD3DQUERYCOUNTDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERYCOUNT.
old-location: display\dd_getd3dquerycountdata.htm
tech.root: display
ms.assetid: 2e5877d9-a584-40fb-8e96-2ffae00df857
ms.date: 05/10/2018
ms.keywords: DD_GETD3DQUERYCOUNTDATA, DD_GETD3DQUERYCOUNTDATA structure [Display Devices], _DD_GETD3DQUERYCOUNTDATA, d3dhal/DD_GETD3DQUERYCOUNTDATA, d3dstrct_d97e6eb4-0ecd-4459-9256-eee9bb36bb78.xml, display.dd_getd3dquerycountdata
ms.topic: struct
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
- DD_GETD3DQUERYCOUNTDATA
product:
- Windows
targetos: Windows
req.typenames: DD_GETD3DQUERYCOUNTDATA
---

# _DD_GETD3DQUERYCOUNTDATA structure


## -description



   DirectX 9.0 and later versions only.
   

DD_GETD3DQUERYCOUNTDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERYCOUNT.


## -struct-fields




### -field gdi2

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data for the query.


### -field dwNumQueries

Receives the number of supported query types.


## -remarks



To handle D3DGDI2_TYPE_GETD3DQUERYCOUNT, the driver must store the number of query types that it supports in the <b>dwNumQueries</b> member of DD_GETD3DQUERYCOUNTDATA. Query types are represented by values in the D3DQUERYTYPE enumeration.




## -see-also




D3DDP2OP_CREATEQUERY



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getd3dquerydata">DD_GETD3DQUERYDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>
 

 

