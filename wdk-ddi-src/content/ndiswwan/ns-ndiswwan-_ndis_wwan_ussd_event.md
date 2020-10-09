---
UID: NS:ndiswwan._NDIS_WWAN_USSD_EVENT
title: _NDIS_WWAN_USSD_EVENT (ndiswwan.h)
description: The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS event.
old-location: netvista\ndis_wwan_ussd_event.htm
tech.root: netvista
ms.assetid: 11533451-31EC-4C55-9675-5AC7D25B6C9D
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_USSD_EVENT structure"]
ms.keywords: "*PNDIS_WWAN_USSD_EVENT, NDIS_WWAN_USSD_EVENT, NDIS_WWAN_USSD_EVENT structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_USSD_EVENT, PNDIS_WWAN_USSD_EVENT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_USSD_EVENT, ndiswwan/NDIS_WWAN_USSD_EVENT, ndiswwan/PNDIS_WWAN_USSD_EVENT, netvista.ndis_wwan_ussd_event"
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
req.irql: 
targetos: Windows
req.typenames: NDIS_WWAN_USSD_EVENT, *PNDIS_WWAN_USSD_EVENT
f1_keywords:
 - _NDIS_WWAN_USSD_EVENT
 - ndiswwan/_NDIS_WWAN_USSD_EVENT
 - PNDIS_WWAN_USSD_EVENT
 - ndiswwan/PNDIS_WWAN_USSD_EVENT
 - NDIS_WWAN_USSD_EVENT
 - ndiswwan/NDIS_WWAN_USSD_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_USSD_EVENT
---

# _NDIS_WWAN_USSD_EVENT structure


## -description

The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS event.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_USSD_EVENT structure. The MB Service sets the header with the values that are shown in the following table when it
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
NDIS_WWAN_USSD_EVENT_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_USSD_EVENT)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field uStatus

A miniport driver must set this to WWAN_STATUS_SUCCESS for successful OID_WWAN_USSD query execution.
     

The following table shows the other possible error status codes (other members need not be updated by
     miniport driver).

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
Device requires PIN value input.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Unable to get visible list.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
A SIM card is not inserted in the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PROVIDERS_NOT_FOUND

</td>
<td>
No providers are found. Device seems to be in no network coverage.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
The device is busy and unable to scan. This can happen if the device does a destructive scan (for
        example, a scan may result in current registered state or PDP activation to be changed to deregister
        or PDP deactivation).

</td>
</tr>
<tr>
<td>
WWAN_STATUS_RADIO_POWER_OFF

</td>
<td>
Unable to scan. Radio is switched off.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SERVICE_NOT_ACTIVATED

</td>
<td>
Service activation has failed. Subscription has expired. Device does not allow scanning.

</td>
</tr>
</table>

### -field UssdEvent

A formatted 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ussd_event">WWAN_USSD_EVENT</a> object that represents a
     USSD event.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ussd_event">WWAN_USSD_EVENT</a>