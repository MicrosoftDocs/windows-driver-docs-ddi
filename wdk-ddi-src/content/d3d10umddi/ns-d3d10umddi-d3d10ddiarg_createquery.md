---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEQUERY
title: D3D10DDIARG_CREATEQUERY
author: windows-driver-content
description: The D3D10DDIARG_CREATEQUERY structure describes the query to create.
old-location: display\d3d10ddiarg_createquery.htm
old-project: display
ms.assetid: 1042f401-fbdd-47ee-8cfc-1bca331ac722
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDIARG_CREATEQUERY, D3D10DDIARG_CREATEQUERY structure [Display Devices], UMDisplayDriver_Dx10param_Structs_92f45053-c4aa-4bcd-b2ab-570aaf95cfe3.xml, d3d10umddi/D3D10DDIARG_CREATEQUERY, display.d3d10ddiarg_createquery
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_CREATEQUERY
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATEQUERY
---

# D3D10DDIARG_CREATEQUERY structure


## -description


The D3D10DDIARG_CREATEQUERY structure describes the query to create.


## -struct-fields




### -field Query

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>-typed value that identifies the type of query to create. 


### -field MiscFlags

[in] A valid bitwise OR of flag values for the query. Currently, the Direct3D runtime supports only the D3D10DDI_QUERY_MISCFLAG_PREDICATEHINT (0x1) flag. This flag is set along with a D3DQUERYTYPE_OCCLUSIONPREDICATE query type to indicate that the predicate query is a hint. If a predicate query is indicated as a hint (versus guaranteed), no result is ever propagated back to the calling application. 


## -remarks



The Direct3D runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/abe6a82f-1613-4c74-9e81-01939db74bfd">CreateQuery(D3D10)</a> function with a query type to create resources for a query. For information about the type of resources the user-mode display driver creates, see the values of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a> enumeration.




## -see-also




<a href="https://msdn.microsoft.com/59a59aa8-085e-4bf8-8a6f-e08f2aecd894">CalcPrivateQuerySize</a>



<a href="https://msdn.microsoft.com/abe6a82f-1613-4c74-9e81-01939db74bfd">CreateQuery(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATEQUERY structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

