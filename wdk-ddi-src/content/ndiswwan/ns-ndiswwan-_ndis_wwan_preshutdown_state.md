---
UID: NS:ndiswwan._NDIS_WWAN_PRESHUTDOWN_STATE
title: _NDIS_WWAN_PRESHUTDOWN_STATE (ndiswwan.h)
description: The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status.
old-location: netvista\ndis_wwan_preshutdown_state.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_PRESHUTDOWN_STATE structure"]
ms.keywords: "*PNDIS_WWAN_PRESHUTDOWN_STATE, NDIS_WWAN_PRESHUTDOWN_STATE, NDIS_WWAN_PRESHUTDOWN_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PRESHUTDOWN_STATE, PNDIS_WWAN_PRESHUTDOWN_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_PRESHUTDOWN_STATE, ndiswwan/NDIS_WWAN_PRESHUTDOWN_STATE, ndiswwan/PNDIS_WWAN_PRESHUTDOWN_STATE, netvista.ndis_wwan_preshutdown_state"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 10, version 1511.
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
targetos: Windows
req.typenames: NDIS_WWAN_PRESHUTDOWN_STATE, *PNDIS_WWAN_PRESHUTDOWN_STATE
f1_keywords:
 - _NDIS_WWAN_PRESHUTDOWN_STATE
 - ndiswwan/_NDIS_WWAN_PRESHUTDOWN_STATE
 - PNDIS_WWAN_PRESHUTDOWN_STATE
 - ndiswwan/PNDIS_WWAN_PRESHUTDOWN_STATE
 - NDIS_WWAN_PRESHUTDOWN_STATE
 - ndiswwan/NDIS_WWAN_PRESHUTDOWN_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_PRESHUTDOWN_STATE
 - PNDIS_WWAN_PRESHUTDOWN_STATE
 - NDIS_WWAN_PRESHUTDOWN_STATE
---

# _NDIS_WWAN_PRESHUTDOWN_STATE structure


## -description

The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PRESHUTDOWN_STATE
     structure. 

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
 NDIS_WWAN_PRESHUTDOWN_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PRESHUTDOWN_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field uStatus

The following table shows the possible status codes.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
Pre-shutdown operations are complete and the host can power down the MBB driver.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The modem does not support pre-shutdown notifications.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-wwan-preshutdown-state">NDIS_STATUS_WWAN_PRESHUTDOWN_STATE</a>



<a href="/windows-hardware/drivers/network/oid-wwan-preshutdown">OID_WWAN_PRESHUTDOWN</a>

