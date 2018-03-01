---
UID: NS:d3dumddi._D3DDDIARG_GETQUERYDATA
title: "_D3DDDIARG_GETQUERYDATA"
author: windows-driver-content
description: The D3DDDIARG_GETQUERYDATA structure contains query information that was retrieved from the user-mode display driver.
old-location: display\d3dddiarg_getquerydata.htm
old-project: display
ms.assetid: 98c6ada1-89a4-4cbd-bb6c-98c190fa15d8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_GETQUERYDATA, D3DDDIARG_GETQUERYDATA structure [Display Devices], UMDisplayDriver_param_Structs_7f9fefc5-6bce-4a76-9841-d91a40710d4a.xml, _D3DDDIARG_GETQUERYDATA, d3dumddi/D3DDDIARG_GETQUERYDATA, display.d3dddiarg_getquerydata
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
-	D3DDDIARG_GETQUERYDATA
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETQUERYDATA
---

# _D3DDDIARG_GETQUERYDATA structure


## -description


The D3DDDIARG_GETQUERYDATA structure contains query information that was retrieved from the user-mode display driver.


## -syntax


````
typedef struct _D3DDDIARG_GETQUERYDATA {
  HANDLE hQuery;
  VOID   *pData;
} D3DDDIARG_GETQUERYDATA;
````


## -struct-fields




### -field hQuery

[in] The handle to the query that was created by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function.


### -field pData

[out] A pointer to a buffer that the driver fills with data that is related to a query, if the query type is one that requires data. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getquerydata.md">GetQueryData</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GETQUERYDATA structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

