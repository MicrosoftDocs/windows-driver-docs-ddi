---
UID: NS:windot11._DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS
title: _DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS (windot11.h)
description: The confirmation parameters for a Group Owner (GO) negotiation response indication are specified in a DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure.
old-location: netvista\dot11_send_go_negotiation_confirmation_parameters.htm
tech.root: netvista
ms.assetid: CBEDFDCA-A43D-47E3-AE3F-2C25E50D7A70
ms.date: 02/16/2018
keywords: ["DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure"]
ms.keywords: "*PDOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, PDOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, netvista.dot11_send_go_negotiation_confirmation_parameters, windot11/DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, windot11/PDOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS"
f1_keywords:
 - "windot11/DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS"
 - "DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Windot11.h
api_name:
- DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS
targetos: Windows
req.typenames: DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, *PDOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The confirmation parameters for a Group Owner (GO) negotiation response indication are specified in a <b>DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS</b> structure. This structure is sent with an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-go-negotiation-confirmation">OID_DOT11_WFD_SEND_GO_NEGOTIATION_CONFIRMATION</a> request to the miniport.


## -syntax


```cpp
typedef struct _DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS {
  NDIS_OBJECT_HEADER         Header;
  DOT11_MAC_ADDRESS          PeerDeviceAddress;
  DOT11_DIALOG_TOKEN         DialogToken;
  PVOID                      ResponseContext;
  ULONG                      uSendTimeout;
  DOT11_WFD_STATUS_CODE      Status;
  DOT11_WFD_GROUP_CAPABILITY GroupCapability;
  DOT11_WFD_GROUP_ID         GroupID;
  BOOLEAN                    bUseGroupID;
  ULONG                      uIEsOffset;
  ULONG                      uIEsLength;
} DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS, *PDOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS;
```


## -struct-fields




### -field Header

Specifies the type, revision and size of the <b>DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_SEND_GO_NEGOTIATION_CONFIRMATION_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field PeerDeviceAddress

The Peer-to-Peer (P2P) address of the Wi-Fi Direct (WFD) device that the GO negotiation confirmation is sent to.


### -field DialogToken

The dialog token received from the GO negotiation response packet. This dialog token must be included in  the GO negotiation confirmation  packet.


### -field ResponseContext

Miniport context data included in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-received-go-negotiation-response">NDIS_STATUS_DOT11_WFD_RECEIVED_GO_NEGOTIATION_RESPONSE</a> indication.


### -field uSendTimeout

The maximum time, in milliseconds, allowed to send the GO negotiation response. If the timeout expires before the miniport has successfully transmitted the GO negotiation confirmation, it should indicate the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-go-negotiation-confirmation-send-complete">NDIS_STATUS_DOT11_WFD_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE</a> with a failure status.


### -field Status

Status information to include in the GO  negotiation confirmation.


### -field GroupCapability

The capability values that are included in the Group Capability bitmask of the Peer-to-Peer (P2P) Capability Information Element (IE) in  a GO negotiation confirmation.


### -field GroupID

The group identifier to include in the Group ID attribute of the GO negotiation confirmation.


### -field bUseGroupID

If TRUE, the value in <b>GroupID</b> should be included in the GO negotiation confirmation.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) the Wi-Fi Direct (WFD) port must add to the GO negotiation confirmation packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-received-go-negotiation-response">NDIS_STATUS_DOT11_WFD_RECEIVED_GO_NEGOTIATION_RESPONSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-go-negotiation-confirmation">OID_DOT11_WFD_SEND_GO_NEGOTIATION_CONFIRMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-dot11-wfd-go-negotiation-confirmation-send-complete">NDIS_STATUS_DOT11_WFD_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE</a>



 

 


