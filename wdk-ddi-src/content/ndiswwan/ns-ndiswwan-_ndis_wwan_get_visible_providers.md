---
UID: NS:ndiswwan._NDIS_WWAN_GET_VISIBLE_PROVIDERS
title: "_NDIS_WWAN_GET_VISIBLE_PROVIDERS"
author: windows-driver-content
description: The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers.
old-location: netvista\ndis_wwan_get_visible_providers.htm
old-project: netvista
ms.assetid: C1AF383A-2D9D-4B2F-A925-D138E1B7AA4F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_WWAN_GET_VISIBLE_PROVIDERS, NDIS_WWAN_GET_VISIBLE_PROVIDERS, NDIS_WWAN_GET_VISIBLE_PROVIDERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_GET_VISIBLE_PROVIDERS, PNDIS_WWAN_GET_VISIBLE_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_GET_VISIBLE_PROVIDERS, ndiswwan/NDIS_WWAN_GET_VISIBLE_PROVIDERS, ndiswwan/PNDIS_WWAN_GET_VISIBLE_PROVIDERS, netvista.ndis_wwan_get_visible_providers"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_GET_VISIBLE_PROVIDERS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_GET_VISIBLE_PROVIDERS, *PNDIS_WWAN_GET_VISIBLE_PROVIDERS
---

# _NDIS_WWAN_GET_VISIBLE_PROVIDERS structure


## -description


The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_GET_VISIBLE_PROVIDERS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_GET_VISIBLE_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_GET_VISIBLE_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field VisibleProviders

A formatted WWAN_GET_VISIBLE_PROVIDERS object that provides additional information to the miniport about the type of providers to return.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831879">WWAN_GET_VISIBLE_PROVIDERS</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_GET_VISIBLE_PROVIDERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
