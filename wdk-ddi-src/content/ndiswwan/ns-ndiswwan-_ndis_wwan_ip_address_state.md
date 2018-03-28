---
UID: NS:ndiswwan._NDIS_WWAN_IP_ADDRESS_STATE
title: "_NDIS_WWAN_IP_ADDRESS_STATE"
author: windows-driver-content
description: The NDIS_WWAN_IP_ADDRESS_STATE structure represents the IP address of a PDP context.
old-location: netvista\ndis_wwan_ip_address_state.htm
old-project: netvista
ms.assetid: 114EDC8D-2FD2-4602-827E-9737638E49AC
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_WWAN_IP_ADDRESS_STATE, NDIS_WWAN_IP_ADDRESS_STATE, NDIS_WWAN_IP_ADDRESS_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_IP_ADDRESS_STATE, PNDIS_WWAN_IP_ADDRESS_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_IP_ADDRESS_STATE, ndiswwan/NDIS_WWAN_IP_ADDRESS_STATE, ndiswwan/PNDIS_WWAN_IP_ADDRESS_STATE, netvista.ndis_wwan_ip_address_state"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
-	NDIS_WWAN_IP_ADDRESS_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_IP_ADDRESS_STATE, *PNDIS_WWAN_IP_ADDRESS_STATE
---

# _NDIS_WWAN_IP_ADDRESS_STATE structure


## -description


The NDIS_WWAN_IP_ADDRESS_STATE structure represents the IP address of a PDP context.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_IP_ADDRESS_STATE structure. The MB
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
NDIS_WWAN_IP_ADDRESS_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_IP_ADDRESS_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field WwanIpAddressState

The PDP context's IP address.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449757">WWAN_IP_ADDRESS_STATE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_IP_ADDRESS_STATE structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

