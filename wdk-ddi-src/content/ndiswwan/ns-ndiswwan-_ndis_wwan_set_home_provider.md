---
UID: NS:ndiswwan._NDIS_WWAN_SET_HOME_PROVIDER
title: _NDIS_WWAN_SET_HOME_PROVIDER
author: windows-driver-content
description: The NDIS_WWAN_SET_HOME_PROVIDER structure describes a home provider.
old-location: netvista\ndis_wwan_set_home_provider.htm
old-project: netvista
ms.assetid: C0B1A72D-713B-48FF-8D1A-E9752569C10E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_wwan_set_home_provider, PNDIS_WWAN_SET_HOME_PROVIDER structure pointer [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_HOME_PROVIDER, ndiswwan/NDIS_WWAN_SET_HOME_PROVIDER, *PNDIS_WWAN_SET_HOME_PROVIDER, NDIS_WWAN_SET_HOME_PROVIDER structure [Network Drivers Starting with Windows Vista], NDIS_WWAN_SET_HOME_PROVIDER, _NDIS_WWAN_SET_HOME_PROVIDER, ndiswwan/PNDIS_WWAN_SET_HOME_PROVIDER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8 and later versions of Windows.
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndiswwan.h
apiname: 
-	NDIS_WWAN_SET_HOME_PROVIDER
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_HOME_PROVIDER, *PNDIS_WWAN_SET_HOME_PROVIDER
---

# _NDIS_WWAN_SET_HOME_PROVIDER structure


## -description


The NDIS_WWAN_SET_HOME_PROVIDER structure describes a home provider.


## -syntax


````
typedef struct _NDIS_WWAN_SET_HOME_PROVIDER {
  NDIS_OBJECT_HEADER Header;
  WWAN_PROVIDER2     HomeProvider;
} NDIS_WWAN_SET_HOME_PROVIDER, *PNDIS_WWAN_SET_HOME_PROVIDER;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_HOME_PROVIDER structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
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
NDIS_WWAN_SET_HOME_PROVIDER_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_HOME_PROVIDER)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field HomeProvider

A formatted WWAN_PROVIDER2 object that represents the details of the home provider to be set.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_provider2.md">WWAN_PROVIDER2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_HOME_PROVIDER structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

