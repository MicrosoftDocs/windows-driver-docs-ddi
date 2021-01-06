---
UID: NS:windot11._DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
title: _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_started_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure"]
ms.keywords: "*PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS, DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_f09f57cb-9f15-444c-b09f-d97f016e86a2.xml, PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS, PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, netvista.dot11_incoming_assoc_started_parameters, windot11/DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, windot11/PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.typenames: DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, *PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS
f1_keywords:
 - _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
 - windot11/_DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
 - PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS
 - windot11/PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS
 - DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
 - windot11/DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_INCOMING_ASSOC_STARTED_PARAMETERS
product:
 - Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure specifies that the NIC has received the first
  valid 802.11 authentication request from a peer station on an infrastructure BSS.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure. This member
     is formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="Type"></a><a id="type"></a><a id="TYPE"></a>Type

</td>
<td width="60%">
This member must be set to NDIS_OBJECT_TYPE_DEFAULT.

</td>
</tr>
<tr>
<td width="40%">
<a id="Revision"></a><a id="revision"></a><a id="REVISION"></a>Revision

</td>
<td width="60%">
This member must be set to DOT11_INCOMING_ASSOC_STARTED_PARAMETERS_REVISION_1.

</td>
</tr>
<tr>
<td width="40%">
<a id="Size"></a><a id="size"></a><a id="SIZE"></a>Size

</td>
<td width="60%">
This member must be set to
       <b>sizeof</b>(DOT11_INCOMING_ASSOC_STARTED_PARAMETERS).

</td>
</tr>
</table>
 

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field PeerMacAddr

The media access control (MAC) address of the peer station that sent an 802.11 authentication
     request.

## -syntax

```cpp
typedef struct _DOT11_INCOMING_ASSOC_STARTED_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
} DOT11_INCOMING_ASSOC_STARTED_PARAMETERS, *PDOT11_INCOMING_ASSOC_STARTED_PARAMETERS;
```

## -remarks

The Native 802.11 miniport driver includes a DOT11_INCOMING_ASSOC_STARTED_PARAMETERS structure when
    the driver makes an
    <a href="/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-started">
    NDIS_STATUS_DOT11_INCOMING_ASSOC_STARTED</a> status indication.

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-started">
   NDIS_STATUS_DOT11_INCOMING_ASSOC_STARTED</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
