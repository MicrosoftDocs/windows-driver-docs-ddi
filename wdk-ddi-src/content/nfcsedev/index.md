---
UID: NA:nfcsedev
ms.assetid: 71f179ce-e2f5-3602-a35a-5134da7d7128
ms.author: windowsdriverdev
ms.date: 04/02/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Nfcsedev.h header


## -description


This header is used by nfpdrivers. For more information, see:

- [Near field communications (NFC)](../_nfpdrivers/index.md)

The NFC Secure Element (SE) DDI allows callers to the NFC device driver to enumerate, communicate with, and configure the secure elements accessible from the device. 

The following is a unique GUID that identifies the NFC SE.

The IOCTLs described in this section comprise the SE device driver interface and all of them use METHOD_BUFFERED and FILE_ANY_ACCESS.

## Secure element DDI overview

<table>
<tr>
<th>Usage</th>
<th>DDI</th>
</tr>
<tr>
<td>Retrieve NFCC capabilities</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_get_nfcc_capabilities"><b>IOCTL_NFCSE_GET_NFCC_CAPABILITIES</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_nfcc_capabilities"><b>SECURE_ELEMENT_NFCC_CAPABILITIES</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
<tr>
<td>Enumerate secure elements</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_enum_endpoints"><b>IOCTL_NFCSE_ENUM_ENDPOINTS</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_type"><b>SECURE_ELEMENT_TYPE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_endpoint_list"><b>SECURE_ELEMENT_ENDPOINT_LIST</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_endpoint_info"><b>SECURE_ELEMENT_ENDPOINT_INFO</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
<tr>
<td>Configure secure elements</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_set_card_emulation_mode"><b>IOCTL_NFCSE_SET_CARD_EMULATION_MODE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.secure_element_set_card_emulation_mode_info"><b>SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.secure_element_set_card_emulation_mode"><b>SECURE_ELEMENT_CARD_EMULATION_MODE</b></mshelp:link>
</dd>
<dd></dd>
</dl>
</td>
</tr>
<tr>
<td>Secure element events</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_subscribe_for_event"><b>IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_get_next_event"><b>IOCTL_NFCSE_GET_NEXT_EVENT</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.secure_element_event_subscription_info"><b>SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.secure_element_event_info"><b>SECURE_ELEMENT_EVENT_INFO</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_event_type"><b>SECURE_ELEMENT_EVENT_TYPE</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
<tr>
<td>Manage listen mode routing configuration</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_get_routing_table"><b>IOCTL_NFCSE_GET_ROUTING_TABLE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_set_routing_table"><b>IOCTL_NFCSE_SET_ROUTING_TABLE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_routing_type"><b>SECURE_ELEMENT_ROUTING_TYPE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_tech_routing_info"><b>SECURE_ELEMENT_TECH_ROUTING_INFO</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_proto_routing_info"><b>SECURE_ELEMENT_PROTO_ROUTING_INFO</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_aid_routing_info"><b>SECURE_ELEMENT_AID_ROUTING_INFO</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_routing_table_entry"><b>SECURE_ELEMENT_ROUTING_TABLE_ENTRY</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_routing_table"><b>SECURE_ELEMENT_ROUTING_TABLE</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
<tr>
<td>Handle HCE traffic</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_hce_remote_recv"><b>IOCTL_NFCSE_HCE_REMOTE_RECV</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcse_hce_remote_send"><b>IOCTL_NFCSE_HCE_REMOTE_SEND</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.secure_element_hce_activation_payload"><b>SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._secure_element_hce_data_packet"><b>SECURE_ELEMENT_HCE_DATA_PACKET</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
</table>

## Related topics

Send comments about this topic to Microsoft

