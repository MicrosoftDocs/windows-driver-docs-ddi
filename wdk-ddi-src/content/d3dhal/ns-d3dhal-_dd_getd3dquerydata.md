---
UID: NS:d3dhal._DD_GETD3DQUERYDATA
title: _DD_GETD3DQUERYDATA
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_GETD3DQUERYDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERY.
old-location: display\dd_getd3dquerydata.htm
old-project: display
ms.assetid: a3bacd56-c25a-45d1-bd9f-b19bc1f95c8f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_GETD3DQUERYDATA, DD_GETD3DQUERYDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DD_GETD3DQUERYDATA
req.alt-loc: d3dhal.h
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
req.typenames: DD_GETD3DQUERYDATA
---

# _DD_GETD3DQUERYDATA structure



## -description

   DirectX 9.0 and later versions only.
   

DD_GETD3DQUERYDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETD3DQUERY.



## -syntax

````
typedef struct _DD_GETD3DQUERYDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  union {
    DWORD        dwQueryIndex;
    D3DQUERYTYPE QueryType;
  };
} DD_GETD3DQUERYDATA;
````


## -struct-fields

### -field gdi2

Specifies a <a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwQueryIndex

Specifies the index of the query type to return.


### -field QueryType

Receives a value from the D3DQUERYTYPE enumeration that specifies the actual query capability.


## -remarks
The runtime identifies the query type to be returned with an integer index whose value varies between zero and one less than the number of supported query types that were reported earlier by the driver in a D3DGDI2_TYPE_GETD3DQUERYCOUNT query. How these indices are mapped to actual query types is left to the driver. However, each index must map uniquely to one supported query type. The order in which the query types are reported is not significant. 

When processing this <b>GetDriverInfo2</b> request the driver should read the value in the union as if it were the <b>dwQueryIndex</b> member and map that value to one of the supported query types (probably by using the value in <b>dwQueryIndex</b> as an index into an array of D3DQUERYTYPE values). The driver should then copy that query type into the union as if it were the <b>QueryType</b> member. The runtime guarantees that it only passes an index to the driver that is in the range zero to one less than the number of query types reported by the driver. The range of the index should be validated in the debug driver build.

For more information about D3DQUERYTYPE, see the DirectX SDK documentation.


## -see-also
<dl>
<dt>D3DDP2OP_CREATEQUERY</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_dd_getd3dquerycountdata.md">DD_GETD3DQUERYCOUNTDATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETD3DQUERYDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

