---
UID: NS:ndiswwan._NDIS_WWAN_USSD_EVENT
title: _NDIS_WWAN_USSD_EVENT
author: windows-driver-content
description: The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS event.
old-location: netvista\ndis_wwan_ussd_event.htm
old-project: netvista
ms.assetid: 11533451-31EC-4C55-9675-5AC7D25B6C9D
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_USSD_EVENT, NDIS_WWAN_USSD_EVENT, *PNDIS_WWAN_USSD_EVENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_USSD_EVENT
req.alt-loc: ndiswwan.h
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
req.typenames: NDIS_WWAN_USSD_EVENT, *PNDIS_WWAN_USSD_EVENT
---

# _NDIS_WWAN_USSD_EVENT structure



## -description
The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS event.



## -syntax

````
typedef struct _NDIS_WWAN_USSD_EVENT {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_USSD_EVENT    UssdEvent;
} NDIS_WWAN_USSD_EVENT, *PNDIS_WWAN_USSD_EVENT;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


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
     <a href="..\wwan\ns-wwan-_wwan_ussd_event.md">WWAN_USSD_EVENT</a> object that represents a
     USSD event.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_ussd_event.md">WWAN_USSD_EVENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_USSD_EVENT structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

