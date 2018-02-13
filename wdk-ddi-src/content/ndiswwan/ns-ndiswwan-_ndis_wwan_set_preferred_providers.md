---
UID: NS:ndiswwan._NDIS_WWAN_SET_PREFERRED_PROVIDERS
title: "_NDIS_WWAN_SET_PREFERRED_PROVIDERS"
author: windows-driver-content
description: The NDIS_WWAN_SET_PREFERRED_PROVIDERS structure represents the list of preferred providers associated with the MB device.
old-location: netvista\ndis_wwan_set_preferred_providers.htm
old-project: netvista
ms.assetid: 6741d440-0e17-4b2d-a642-0335d1f936cf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_WWAN_SET_PREFERRED_PROVIDERS structure [Network Drivers Starting with Windows Vista], NDIS_WWAN_SET_PREFERRED_PROVIDERS, PNDIS_WWAN_SET_PREFERRED_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_PREFERRED_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_PROVIDERS, ndiswwan/NDIS_WWAN_SET_PREFERRED_PROVIDERS, WwanRef_9e9b42a9-813f-4440-a112-9af4bc172d4e.xml, ndiswwan/PNDIS_WWAN_SET_PREFERRED_PROVIDERS, netvista.ndis_wwan_set_preferred_providers, PNDIS_WWAN_SET_PREFERRED_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	NDIS_WWAN_SET_PREFERRED_PROVIDERS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PREFERRED_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_PROVIDERS
---

# _NDIS_WWAN_SET_PREFERRED_PROVIDERS structure


## -description


The NDIS_WWAN_SET_PREFERRED_PROVIDERS structure represents the list of preferred providers associated
  with the MB device.


## -syntax


````
typedef struct _NDIS_WWAN_SET_PREFERRED_PROVIDERS {
  NDIS_OBJECT_HEADER Header;
  WWAN_LIST_HEADER   PreferredListHeader;
} NDIS_WWAN_SET_PREFERRED_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_PROVIDERS;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PREFERRED_PROVIDERS
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
NDIS_WWAN_SET_PREFERRED_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PREFERRED_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PreferredListHeader

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a> object that represents a
     list of preferred providers to associate with the device.
     

<b>WwanDataClass</b> flags describe the preference of the specific data access technology and can be set
     to any combination within its own cellular class.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_PREFERRED_PROVIDERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

