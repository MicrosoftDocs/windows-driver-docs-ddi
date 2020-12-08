---
UID: NS:ndiswwan._NDIS_WWAN_READY_INFO
title: _NDIS_WWAN_READY_INFO (ndiswwan.h)
description: The NDIS_WWAN_READY_INFO structure represents the ready-state of the MB device and Subscriber Identity Module (SIM card).
old-location: netvista\ndis_wwan_ready_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_READY_INFO structure"]
ms.keywords: "*PNDIS_WWAN_READY_INFO, NDIS_WWAN_READY_INFO, NDIS_WWAN_READY_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_READY_INFO, PNDIS_WWAN_READY_INFO structure pointer [Network Drivers Starting with Windows Vista], WwanRef_6ae45c84-c13d-4142-b39a-07b3a9f57253.xml, _NDIS_WWAN_READY_INFO, ndiswwan/NDIS_WWAN_READY_INFO, ndiswwan/PNDIS_WWAN_READY_INFO, netvista.ndis_wwan_ready_info"
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
req.irql: 
targetos: Windows
req.typenames: NDIS_WWAN_READY_INFO, *PNDIS_WWAN_READY_INFO
f1_keywords:
 - _NDIS_WWAN_READY_INFO
 - ndiswwan/_NDIS_WWAN_READY_INFO
 - PNDIS_WWAN_READY_INFO
 - ndiswwan/PNDIS_WWAN_READY_INFO
 - NDIS_WWAN_READY_INFO
 - ndiswwan/NDIS_WWAN_READY_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_READY_INFO
---

# _NDIS_WWAN_READY_INFO structure


## -description

The NDIS_WWAN_READY_INFO structure represents the ready-state of the MB device and Subscriber
  Identity Module (SIM card).

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_READY_INFO structure. The
     MB Service sets the header with the values that are shown in the following table when it sends the data
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
NDIS_WWAN_READY_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_READY_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field ReadyInfo

A formatted 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ready_info">WWAN_READY_INFO</a> object that represents the
     device ready-state.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ready_info">WWAN_READY_INFO</a>
