---
UID: NS:d3dumddi._D3DDDIARG_CREATEQUERY
title: "_D3DDDIARG_CREATEQUERY"
author: windows-driver-content
description: The D3DDDIARG_CREATEQUERY structure identifies a query to create.
old-location: display\d3dddiarg_createquery.htm
tech.root: display
ms.assetid: f80224c6-9046-4471-b6c6-eb14f02fc51f
ms.author: windowsdriverdev
ms.date: 5/10/2018
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

[in] A [D3DDDIQUERYTYPE](ne-d3dumddi-_d3dddiquerytype.md)-typed value that indicates the query type to create resources for. 

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
 

 

