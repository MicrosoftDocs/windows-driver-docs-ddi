---
UID: NS:ndiswwan._NDIS_WWAN_PACKET_SERVICE_STATE
title: "_NDIS_WWAN_PACKET_SERVICE_STATE"
author: windows-driver-content
description: The NDIS_WWAN_PACKET_SERVICE_STATE structure represents the packet service attachment state of the MB device.
old-location: netvista\ndis_wwan_packet_service_state.htm
old-project: netvista
ms.assetid: 63dbd674-32b3-4843-8349-706c3c0380e5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_WWAN_PACKET_SERVICE_STATE structure pointer [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PACKET_SERVICE_STATE, _NDIS_WWAN_PACKET_SERVICE_STATE, netvista.ndis_wwan_packet_service_state, WwanRef_b676b582-9e62-4e40-adbf-fe924103ebb6.xml, *PNDIS_WWAN_PACKET_SERVICE_STATE, ndiswwan/NDIS_WWAN_PACKET_SERVICE_STATE, NDIS_WWAN_PACKET_SERVICE_STATE, NDIS_WWAN_PACKET_SERVICE_STATE structure [Network Drivers Starting with Windows Vista], ndiswwan/PNDIS_WWAN_PACKET_SERVICE_STATE
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
-	NDIS_WWAN_PACKET_SERVICE_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_PACKET_SERVICE_STATE, *PNDIS_WWAN_PACKET_SERVICE_STATE
---

# _NDIS_WWAN_PACKET_SERVICE_STATE structure


## -description


The NDIS_WWAN_PACKET_SERVICE_STATE structure represents the packet service attachment state of the MB
  device.


## -syntax


````
typedef struct _NDIS_WWAN_PACKET_SERVICE_STATE {
  NDIS_OBJECT_HEADER  Header;
  WWAN_STATUS         uStatus;
  WWAN_PACKET_SERVICE PacketService;
} NDIS_WWAN_PACKET_SERVICE_STATE, *PNDIS_WWAN_PACKET_SERVICE_STATE;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PACKET_SERVICE_STATE
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
NDIS_WWAN_PACKET_SERVICE_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PACKET_SERVICE_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

A miniport driver must set this to WWAN_STATUS_SUCCESS for unsolicited events
     (NDIS_STATUS_INDICATION::RequestId = 0).
     

WWAN_STATUS_SUCCESS is also set for successful execution of 
     <i>set</i> and 
     <i>query</i> requests.

WWAN_STATUS_SUCCESS should be returned by the miniport driver, if the requested state and the current
     state are same for a 
     <i>set</i> request.

The following table shows the other possible error status codes.

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
Unable to get or set packet service state.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The operation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
</table>
 

Miniport drivers can return the error codes (in addition to the above listed) shown in the following
     table in the event that a packet-attach 
     <i>set</i> request fails.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Packet-attach or packet-detach has failed. More information is set at 
        <b>uNwError</b> member of WWAN_PACKET_SERVICE structure. For other WWAN_STATUS_XXX errors, 
        <b>uNwError</b> should be set to zero.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SERVICE_NOT_ACTIVATED

</td>
<td>
The device does not allow setting packet service state because of service activation failure or
        expired subscription.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PROVIDER_NOT_VISIBLE

</td>
<td>
Provider is not visible for packet service operations.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_REGISTERED

</td>
<td>
The device is not in registered state to perform a packet-attach operation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
SET packet service is not supported by this CDMA-based device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_RADIO_POWER_OFF

</td>
<td>
Unable to packet-attach because the radio is turned off.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
A SIM card is not inserted.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
A bad SIM card is detected.

</td>
</tr>
</table>
 


### -field PacketService

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_packet_service.md">WWAN_PACKET_SERVICE</a> object that
     represents the packet service attachment state of the MB device.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_packet_service.md">WWAN_PACKET_SERVICE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PACKET_SERVICE_STATE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

