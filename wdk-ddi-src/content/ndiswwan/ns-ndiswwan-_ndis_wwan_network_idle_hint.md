---
UID: NS:ndiswwan._NDIS_WWAN_NETWORK_IDLE_HINT
title: "_NDIS_WWAN_NETWORK_IDLE_HINT"
author: windows-driver-content
description: The NDIS_WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface.
old-location: netvista\ndis_wwan_network_idle_hint.htm
old-project: netvista
ms.assetid: 81CA12B7-A7AD-494A-B79A-3EF4A50CB848
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_WWAN_NETWORK_IDLE_HINT, ndiswwan/PNDIS_WWAN_NETWORK_IDLE_HINT, NDIS_WWAN_NETWORK_IDLE_HINT structure [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_NETWORK_IDLE_HINT, _NDIS_WWAN_NETWORK_IDLE_HINT, PNDIS_WWAN_NETWORK_IDLE_HINT, PNDIS_WWAN_NETWORK_IDLE_HINT structure pointer [Network Drivers Starting with Windows Vista], *PNDIS_WWAN_NETWORK_IDLE_HINT, netvista.ndis_wwan_network_idle_hint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of Windows.
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
-	NDIS_WWAN_NETWORK_IDLE_HINT
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_NETWORK_IDLE_HINT, *PNDIS_WWAN_NETWORK_IDLE_HINT
---

# _NDIS_WWAN_NETWORK_IDLE_HINT structure


## -description


The NDIS_WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface.


## -syntax


````
typedef struct _NDIS_WWAN_NETWORK_IDLE_HINT {
  NDIS_OBJECT_HEADER     Header;
  WWAN_NETWORK_IDLE_HINT IdleHint;
} NDIS_WWAN_NETWORK_IDLE_HINT, *PNDIS_WWAN_NETWORK_IDLE_HINT;
````


## -struct-fields




### -field Header

The type, revision, and size of the NDIS_WWAN_NETWORK_IDLE_HINT structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of 
     <b>Header</b> to the following values:



<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>NDIS_WWAN_NETWORK_IDLE_HINT_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>SIZEOF_NDIS_WWAN_NETWORK_IDLE_HINT_1</td>
</tr>
</table>
 


### -field IdleHint

A formatted <a href="..\wwan\ns-wwan-_wwan_network_idle_hint.md">WWAN_NETWORK_IDLE_HINT</a> object that contains the network idle hint.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_network_idle_hint.md">WWAN_NETWORK_IDLE_HINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931089">OID_WWAN_NETWORK_IDLE_HINT</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_NETWORK_IDLE_HINT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

