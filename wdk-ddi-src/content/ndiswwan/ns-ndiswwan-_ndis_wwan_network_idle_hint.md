---
UID: NS:ndiswwan._NDIS_WWAN_NETWORK_IDLE_HINT
title: "_NDIS_WWAN_NETWORK_IDLE_HINT" (ndiswwan.h)
description: The NDIS_WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface.
old-location: netvista\ndis_wwan_network_idle_hint.htm
tech.root: netvista
ms.assetid: 81CA12B7-A7AD-494A-B79A-3EF4A50CB848
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_NETWORK_IDLE_HINT, NDIS_WWAN_NETWORK_IDLE_HINT, NDIS_WWAN_NETWORK_IDLE_HINT structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_NETWORK_IDLE_HINT, PNDIS_WWAN_NETWORK_IDLE_HINT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_NETWORK_IDLE_HINT, ndiswwan/NDIS_WWAN_NETWORK_IDLE_HINT, ndiswwan/PNDIS_WWAN_NETWORK_IDLE_HINT, netvista.ndis_wwan_network_idle_hint"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_NETWORK_IDLE_HINT
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_NETWORK_IDLE_HINT, *PNDIS_WWAN_NETWORK_IDLE_HINT
---

# _NDIS_WWAN_NETWORK_IDLE_HINT structure


## -description


The NDIS_WWAN_NETWORK_IDLE_HINT structure contains a hint for the network interface regarding whether data is expected to be active or idle on the interface.


## -struct-fields




### -field Header

The type, revision, and size of the NDIS_WWAN_NETWORK_IDLE_HINT structure. This member is
     formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

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

A formatted <a href="https://msdn.microsoft.com/library/windows/hardware/dn931165">WWAN_NETWORK_IDLE_HINT</a> object that contains the network idle hint.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931089">OID_WWAN_NETWORK_IDLE_HINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931165">WWAN_NETWORK_IDLE_HINT</a>
 

 

