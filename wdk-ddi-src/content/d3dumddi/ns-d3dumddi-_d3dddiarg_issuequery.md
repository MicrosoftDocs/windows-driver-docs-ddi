---
UID: NS:d3dumddi._D3DDDIARG_ISSUEQUERY
title: "_D3DDDIARG_ISSUEQUERY"
author: windows-driver-content
description: The D3DDDIARG_ISSUEQUERY structure describes how to process a query that was created by the CreateQuery function.
old-location: display\d3dddiarg_issuequery.htm
tech.root: display
ms.assetid: af52d1a3-b537-48d2-ab57-3f798ec83c98
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_ISSUEQUERY, D3DDDIARG_ISSUEQUERY structure [Display Devices], UMDisplayDriver_param_Structs_3fb59dbc-e5de-4d14-9d4b-25934e4e3ded.xml, _D3DDDIARG_ISSUEQUERY, d3dumddi/D3DDDIARG_ISSUEQUERY, display.d3dddiarg_issuequery
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
-	D3DDDIARG_ISSUEQUERY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_ISSUEQUERY
---

# _D3DDDIARG_ISSUEQUERY structure


## -description


The D3DDDIARG_ISSUEQUERY structure describes how to process a query that was created by the <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function. 


## -struct-fields




### -field hQuery

[in] The handle to the query that was created by the <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544575">D3DDDI_ISSUEQUERYFLAGS</a> structure that identifies the type of query to issue. The driver can ignore query requests with <b>Flags</b> set to 0. 

For many query types, start query is never specified (that is, the <b>Begin</b> bit-field flag is never set for many query types). For more information about whether the <b>Begin</b> bit-field flag is set for a query type, see the <b>QueryType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542958">D3DDDIARG_CREATEQUERY</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544575">D3DDDI_ISSUEQUERYFLAGS</a>



<a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a>
 

 

