---
UID: NS:wwan._WWAN_GET_VISIBLE_PROVIDERS
title: _WWAN_GET_VISIBLE_PROVIDERS (wwan.h)
description: The WWAN_GET_VISIBLE_PROVIDERS structure provides information about the type of visible providers to return.
old-location: netvista\wwan_get_visible_providers.htm
tech.root: netvista
ms.assetid: 62516178-11F9-43F3-A70D-42C8FDDAE2DB
ms.date: 05/02/2018
ms.keywords: "*PWWAN_GET_VISIBLE_PROVIDERS, PWWAN_GET_VISIBLE_PROVIDERS, PWWAN_GET_VISIBLE_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], WWAN_GET_VISIBLE_PROVIDERS, WWAN_GET_VISIBLE_PROVIDERS structure [Network Drivers Starting with Windows Vista], _WWAN_GET_VISIBLE_PROVIDERS, netvista.wwan_get_visible_providers, wwan/PWWAN_GET_VISIBLE_PROVIDERS, wwan/WWAN_GET_VISIBLE_PROVIDERS"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	wwan.h
api_name:
-	WWAN_GET_VISIBLE_PROVIDERS
product:
- Windows
targetos: Windows
req.typenames: WWAN_GET_VISIBLE_PROVIDERS, *PWWAN_GET_VISIBLE_PROVIDERS
---

# _WWAN_GET_VISIBLE_PROVIDERS structure


## -description


The WWAN_GET_VISIBLE_PROVIDERS structure provides information about the type of visible providers to return.


## -struct-fields




### -field Action

Provides information about the type of visible providers to return. The following values are defined:

<table></table>
 

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Meaning</b>

</td>
</tr>
<tr>
<td>
WWAN_GET_VISIBLE_PROVIDERS_ALL

</td>
<td>
All providers that are currently visible should be returned.

</td>
</tr>
<tr>
<td>
WWAN_GET_VISIBLE_PROVIDERS_MULTICARRIER

</td>
<td>
Only providers that are currently visible and that can be set as home provider should be returned.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831863">NDIS_WWAN_GET_VISIBLE_PROVIDERS</a>
 

 

