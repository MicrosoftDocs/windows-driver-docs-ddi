---
UID: NC:d3dumddi.PFND3DDDI_DESTROYQUERY
title: PFND3DDDI_DESTROYQUERY
author: windows-driver-content
description: The DestroyQuery function releases resources for a query.
old-location: display\destroyquery.htm
old-project: display
ms.assetid: c4cef278-1771-4903-a5cf-85674463aff8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DestroyQuery, DestroyQuery callback function [Display Devices], PFND3DDDI_DESTROYQUERY, UserModeDisplayDriver_Functions_ce2ecc4e-9e2e-485f-bde3-8800e62c5b8d.xml, d3dumddi/DestroyQuery, display.destroyquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	DestroyQuery
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYQUERY callback


## -description


The <b>DestroyQuery</b> function releases resources for a query.


## -prototype


````
PFND3DDDI_DESTROYQUERY DestroyQuery;

__checkReturn HRESULT APIENTRY DestroyQuery(
  _In_       HANDLE hDevice,
  _In_ const HANDLE hQuery
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param HANDLE








#### - hQuery [in]

 A handle to the query that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function created.


## -returns



<b>DestroyQuery</b> returns S_OK or an appropriate error result if the resources are not released. 




## -remarks



The <b>DestroyQuery</b> function notifies the driver to destroy the query handle that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function previously created. The driver can then release resources that are associated with the query handle.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYQUERY callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

