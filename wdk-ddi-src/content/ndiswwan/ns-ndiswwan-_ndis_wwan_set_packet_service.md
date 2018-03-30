---
UID: NS:ndiswwan._NDIS_WWAN_SET_PACKET_SERVICE
title: "_NDIS_WWAN_SET_PACKET_SERVICE"
author: windows-driver-content
description: The NDIS_WWAN_SET_PACKET_SERVICE structure represents the packet service state of the MB device.
old-location: netvista\ndis_wwan_set_packet_service.htm
old-project: netvista
ms.assetid: bded1e89-3bb5-4241-ab44-875012bfad3a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_WWAN_SET_PACKET_SERVICE, NDIS_WWAN_SET_PACKET_SERVICE, NDIS_WWAN_SET_PACKET_SERVICE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PACKET_SERVICE, PNDIS_WWAN_SET_PACKET_SERVICE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_b98b2778-6d41-426f-85c3-99add8477050.xml, _NDIS_WWAN_SET_PACKET_SERVICE, ndiswwan/NDIS_WWAN_SET_PACKET_SERVICE, ndiswwan/PNDIS_WWAN_SET_PACKET_SERVICE, netvista.ndis_wwan_set_packet_service"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SET_PACKET_SERVICE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PACKET_SERVICE, *PNDIS_WWAN_SET_PACKET_SERVICE
---

# _NDIS_WWAN_SET_PACKET_SERVICE structure


## -description


The NDIS_WWAN_SET_PACKET_SERVICE structure represents the packet service state of the MB
  device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PACKET_SERVICE
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
NDIS_WWAN_SET_PACKET_SERVICE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PACKET_SERVICE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field PacketServiceAction

A value from the 
     <a href="https://msdn.microsoft.com/976e0d67-a03c-4545-b165-4b48062c03b7">
     WWAN_PACKET_SERVICE_ACTION</a> enumeration that represents the packet service action to take.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571211">WWAN_PACKET_SERVICE_ACTION</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_PACKET_SERVICE structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
