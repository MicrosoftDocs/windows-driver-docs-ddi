---
UID: NS:d3dumddi._D3DDDIARG_GETQUERYDATA
title: _D3DDDIARG_GETQUERYDATA (d3dumddi.h)
description: The D3DDDIARG_GETQUERYDATA structure contains query information that was retrieved from the user-mode display driver.
old-location: display\d3dddiarg_getquerydata.htm
tech.root: display
ms.assetid: 98c6ada1-89a4-4cbd-bb6c-98c190fa15d8
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_GETQUERYDATA structure"]
ms.keywords: D3DDDIARG_GETQUERYDATA, D3DDDIARG_GETQUERYDATA structure [Display Devices], UMDisplayDriver_param_Structs_7f9fefc5-6bce-4a76-9841-d91a40710d4a.xml, _D3DDDIARG_GETQUERYDATA, d3dumddi/D3DDDIARG_GETQUERYDATA, display.d3dddiarg_getquerydata
f1_keywords:
 - "d3dumddi/D3DDDIARG_GETQUERYDATA"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_GETQUERYDATA
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_GETQUERYDATA
---

# _D3DDDIARG_GETQUERYDATA structure


## -description


The D3DDDIARG_GETQUERYDATA structure contains query information that was retrieved from the user-mode display driver.


## -struct-fields




### -field hQuery

[in] The handle to the query that was created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createquery">CreateQuery</a> function.


### -field pData

[out] A pointer to a buffer that the driver fills with data that is related to a query, if the query type is one that requires data. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createquery">CreateQuery</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getquerydata">GetQueryData</a>
 

 

