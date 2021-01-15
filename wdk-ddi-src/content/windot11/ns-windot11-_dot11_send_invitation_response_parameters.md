---
UID: NS:windot11._DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
title: _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS (windot11.h)
description: The parameters for a response to a invitation request are specified in a DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_INVITATION_RESPONSE request to the miniport.
old-location: netvista\dot11_send_invitation_response_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure"]
ms.keywords: "*PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS, DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS, PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, netvista.dot11_send_invitation_response_parameters, windot11/DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, windot11/PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
req.typenames: DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, *PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS
f1_keywords:
 - _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - windot11/_DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - windot11/PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - windot11/DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS
 - DOT11_SEND_INVITATION_RESPONSE_PARAMETERS
product:
 - Windows 10 or later.
---

# _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The parameters for a response to a invitation request are specified in a <b>DOT11_SEND_INVITATION_RESPONSE_PARAMETERS</b> structure. This structure is sent with an <a href="/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a> request to the miniport.

## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_SEND_INVITATION_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_SEND_INVITATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_SEND_INVITATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>

### -field ReceiverDeviceAddress

The sender address received from the invitation request packet. This is the device address where the invitation response will be sent.

### -field DialogToken

The dialog token received from the invitation request packet. This dialog token will be used in  the invitation response  packet.

### -field RequestContext

Miniport context data included in the <a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-received-invitation-request">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a> indication.

### -field uSendTimeout

The maximum time, in milliseconds, allowed to send the invitation response. If the timeout expires before the miniport has successfully transmitted the provision discovery response, it should indicate the <a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-invitation-response-send-complete">NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE</a> with a failure status.

### -field Status

Status information to include in the invitation response.

### -field MinimumConfigTimeout

The configuration timeout required by the system  to change its mode of operation to a Peer-to-Peer (P2P) Group Owner or a P2P Client. The miniport driver can set this with a larger value if necessary.

### -field GroupBSSID

The BSSID used by the P2P Group Owner for its P2P Group.

### -field bUseGroupBSSID

If TRUE, the BSSID in <b>GroupBSSID</b> is included in the invitation response. Otherwise, <b>GroupBSSID</b> is not valid.

### -field OperatingChannel

The channel information to include in the Operating Channel attribute of the invitation response.

### -field bUseSpecifiedOperatingChannel

If TRUE, the operatin channel specified in <b>OperatingChannel</b> is included in the invitation response. Otherwise, the miniport driver may choose its own operating channel if <b>Status</b> == <b>DOT11_WFD_STATUS_SUCCESS</b>. If <b>Status</b> != <b>DOT11_WFD_STATUS_SUCCESS</b>, the miniport must not include the operating channel attribute in the inivitation response.

### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) the Wi-Fi Direct (WFD) port must add to the invitation response packet. This offset is from the start of the buffer that contains this structure.

### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.

## -syntax

```cpp
typedef struct _DOT11_SEND_INVITATION_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER              Header;
  DOT11_MAC_ADDRESS               ReceiverDeviceAddress;
  DOT11_DIALOG_TOKEN              DialogToken;
  PVOID                           RequestContext;
  ULONG                           uSendTimeout;
  DOT11_WFD_STATUS_CODE           Status;
  DOT11_WFD_CONFIGURATION_TIMEOUT MinimumConfigTimeout;
  DOT11_MAC_ADDRESS               GroupBSSID;
  BOOLEAN                         bUseGroupBSSID;
  DOT11_WFD_CHANNEL               OperatingChannel;
  BOOLEAN                         bUseSpecifiedOperatingChannel;
  ULONG                           uIEsOffset;
  ULONG                           uIEsLength;
} DOT11_SEND_INVITATION_RESPONSE_PARAMETERS, *PDOT11_SEND_INVITATION_RESPONSE_PARAMETERS;
```

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a>



<a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-received-invitation-request">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a>



<a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-invitation-response-send-complete">NDIS_STATUS_DOT11_WFD_INVITATION_RESPONSE_SEND_COMPLETE</a>

