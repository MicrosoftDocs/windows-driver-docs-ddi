---
UID: NS:d3dumddi._D3DDDIARG_CREATEQUERY
title: "_D3DDDIARG_CREATEQUERY"
author: windows-driver-content
description: The D3DDDIARG_CREATEQUERY structure identifies a query to create.
old-location: display\d3dddiarg_createquery.htm
old-project: display
ms.assetid: f80224c6-9046-4471-b6c6-eb14f02fc51f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_CREATEQUERY, D3DDDIARG_CREATEQUERY structure [Display Devices], UMDisplayDriver_param_Structs_37293319-c280-4363-936a-65a8a5af4c45.xml, _D3DDDIARG_CREATEQUERY, d3dumddi/D3DDDIARG_CREATEQUERY, display.d3dddiarg_createquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_CREATEQUERY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEQUERY
---

# _D3DDDIARG_CREATEQUERY structure


## -description


The D3DDDIARG_CREATEQUERY structure identifies a query to create. 


## -struct-fields




### -field QueryType

[in] A D3DDDIQUERYTYPE-typed value that indicates the query type to create resources for. This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_VCACHE

</td>
<td>
Query at issue end for driver hints about data layout for vertex caching. This query is processed through a call to the driver's <a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a> function in which the <b>End</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543192">D3DDDIARG_ISSUEQUERY</a> structure.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_EVENT

</td>
<td>
Query at issue end for asynchronous events that have occurred.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_OCCLUSION

</td>
<td>
Query for the number of pixels that pass z-testing. These pixels are for primitives that are drawn between an issue begin and an issue end. 

This query is processed between calls to the driver's <a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a> function in which first the <b>Begin</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543192">D3DDDIARG_ISSUEQUERY</a> structure and next the <b>End</b> bit-field flag is set.

This query enables an application to check the occlusion result against 0. A value of 0 is "fully occluded," which means the pixels are not visible from the current camera position.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_TIMESTAMP

</td>
<td>
Query at issue end for the 64-bit timestamp.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_TIMESTAMPDISJOINT

</td>
<td>
This query is used to notify an application whether the counter frequency has changed from the value that is returned from the D3DQUERYTYPE_TIMESTAMP query.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_TIMESTAMPFREQ

</td>
<td>
This query result is <b>TRUE</b> if the values from D3DQUERYTYPE_TIMESTAMP queries cannot be guaranteed to be continuous throughout the duration of the D3DQUERYTYPE_TIMESTAMPDISJOINT query. Otherwise, the query result is <b>FALSE</b>.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_PIPELINETIMINGS

</td>
<td>
Query for the percent of processing time spent on pipeline data.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_INTERFACETIMINGS

</td>
<td>
Query for the percent of processing time spent on data in the driver.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_VERTEXTIMINGS

</td>
<td>
Query for the percent of processing time spent on vertex shader data.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_PIXELTIMINGS

</td>
<td>
Query for the percent of processing time spent on pixel shader data.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_BANDWIDTHTIMINGS

</td>
<td>
Query for throughput measurements for help in understanding the performance of an application.

</td>
</tr>
<tr>
<td>
D3DDDIQUERYTYPE_CACHEUTILIZATION

</td>
<td>
Query for the cache hit-rate performance for textures and indexed vertices.

</td>
</tr>
<tr>
<td>

  
  
  
     D3DDDIQUERYTYPE_COUNTER_DEVICE_DEPENDENT

</td>
<td>
Query for device-dependent counters.

</td>
</tr>
</table>
 


### -field hQuery

[out] A handle to the query. The user-mode display driver's <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function returns this handle to the Microsoft Direct3D runtime. 


## -remarks



The Direct3D runtime uses the handle that is specified by the <b>hQuery</b> member when the runtime calls:

<ul>
<li>
The <a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a> function to process a query.

</li>
<li>
The <a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a> function to retrieve information about the query.

</li>
<li>
The <a href="https://msdn.microsoft.com/c4cef278-1771-4903-a5cf-85674463aff8">DestroyQuery</a> function to destroy the handle.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a>



<a href="https://msdn.microsoft.com/c4cef278-1771-4903-a5cf-85674463aff8">DestroyQuery</a>



<a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a>



<a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a>
 

 

