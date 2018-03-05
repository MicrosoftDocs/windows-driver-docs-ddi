---
UID: NS:ndiswwan._NDIS_WWAN_HOME_PROVIDER2
title: "_NDIS_WWAN_HOME_PROVIDER2"
author: windows-driver-content
description: The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider.
old-location: netvista\ndis_wwan_home_provider2.htm
old-project: netvista
ms.assetid: B01039CF-F4AC-4374-BBB8-ACB204BC40E2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_WWAN_HOME_PROVIDER2, NDIS_WWAN_HOME_PROVIDER2, NDIS_WWAN_HOME_PROVIDER2 structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_HOME_PROVIDER2, PNDIS_WWAN_HOME_PROVIDER2 structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_HOME_PROVIDER2, ndiswwan/NDIS_WWAN_HOME_PROVIDER2, ndiswwan/PNDIS_WWAN_HOME_PROVIDER2, netvista.ndis_wwan_home_provider2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
-	NDIS_WWAN_HOME_PROVIDER2
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_HOME_PROVIDER2, *PNDIS_WWAN_HOME_PROVIDER2
---

# _NDIS_WWAN_HOME_PROVIDER2 structure


## -description


The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider.


## -syntax


````
typedef struct _NDIS_WWAN_HOME_PROVIDER2 {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_PROVIDER2     Provider;
} NDIS_WWAN_HOME_PROVIDER2, *PNDIS_WWAN_HOME_PROVIDER2;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_HOME_PROVIDER2 structure. The MB
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
NDIS_WWAN_HOME_PROVIDER_REVISION_2

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_HOME_PROVIDER2)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the home provider operation.


### -field Provider

A formatted <a href="..\wwan\ns-wwan-_wwan_provider2.md">WWAN_PROVIDER2</a> object that describes the details of a home network provider.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_provider2.md">WWAN_PROVIDER2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_HOME_PROVIDER2 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

