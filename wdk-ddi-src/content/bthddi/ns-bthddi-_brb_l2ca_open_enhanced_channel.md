---
UID: NS:bthddi._BRB_L2CA_OPEN_ENHANCED_CHANNEL
title: _BRB_L2CA_OPEN_ENHANCED_CHANNEL (bthddi.h)
description: The _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure is used to open an enhanced L2CAP channel to a remote device, or send a response for accepting/rejecting an incoming enhanced L2CAP connection request that was initiated by a remote device.
old-location: bltooth\_brb_l2ca_open_enhanced_channel.htm
tech.root: bltooth
ms.date: 05/12/2021
keywords: ["BRB_L2CA_OPEN_ENHANCED_CHANNEL structure"]
ms.keywords: BRB_L2CA_OPEN_ENHANCED_CHANNEL, BRB_L2CA_OPEN_ENHANCED_CHANNEL structure [Bluetooth Devices], PBRB_L2CA_OPEN_ENHANCED_CHANNEL, PBRB_L2CA_OPEN_ENHANCED_CHANNEL structure pointer [Bluetooth Devices], _BRB_L2CA_OPEN_ENHANCED_CHANNEL, _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure [Bluetooth Devices], bltooth._brb_l2ca_open_enhanced_channel, bltooth.brb_l2ca_open_enhanced_channel, bthddi/PBRB_L2CA_OPEN_ENHANCED_CHANNEL, bthddi/_BRB_L2CA_OPEN_ENHANCED_CHANNEL
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows
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
req.typenames: 
f1_keywords:
 - _BRB_L2CA_OPEN_ENHANCED_CHANNEL
 - bthddi/_BRB_L2CA_OPEN_ENHANCED_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthddi.h
api_name:
 - _BRB_L2CA_OPEN_ENHANCED_CHANNEL
---

# _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure

## -description

The _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure is used to open an enhanced L2CAP channel to a remote device, or send a response for accepting/rejecting an incoming enhanced L2CAP connection request that was initiated by a remote device.

## -struct-fields

### -field Hdr

A [BRB_HEADER](./ns-bthddi-_brb_header.md) structure that contains information about the current BRB.

### -field ChannelHandle

Handle used to identify the connection upon a successful connect. When sending a **BRB_L2CA_OPEN_CHANNEL**, this will be filled in when the BRB completes.  When sending a **BRB_L2CA_OPEN_CHANNEL_RESPONSE** request, this must be filled in by the server before sending down the BRB. The value assigned should be `INDICATION_PARAMETERS::ConnectionHandle` which was passed in during the IndicationRemoteConnect.

### -field Response

Used only with **BRB_L2CA_OPEN_CHANNEL_RESPONSE**. One of the CONNECT_RSP_RESULT_Xxx values is used.

If the BRB returns with a status of STATUS_REQUEST_NOT_ACCEPTED, then *Response* will contain the negative response from the remote host.

### -field ResponseStatus

If *Response* is equal to CONNECT_RSP_RESULT_PENDING, then this field is valid. One of the CONNECT_RSP_STATUS_XXX values is used.

### -field Psm

The Protocol/Service Multiplexer (PSM) that the channel uses to connect to the remote device. When used with a **BRB_L2CA_OPEN_ENHANCED_CHANNEL** request, this member is set as an input field. When used with a **BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE** request, this member is used as an output field.

### -field ChannelFlags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in the following table:

| Flag | Description |
| ---- | ----------- |
| CF_LINK_AUTHENTICATED | The link must be authenticated. |
| CF_LINK_ENCRYPTED | The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag. |
| CF_LINK_SUPPRESS_PIN | The profile driver indicates its preference that users not be prompted for a PIN. |

### -field BtAddress

The Bluetooth address of the device for which the connection is intended.

### -field ConfigOut

The substructure that contains parameter settings for a **BRB_L2CA_OPEN_ENHANCED_CHANNEL** BRB sent to a remote device.

### -field ConfigOut.Flags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in the following table:

| Flag | Description |
| ---- | ----------- |
| CF_LINK_AUTHENTICATED | The link must be authenticated. |
| CF_LINK_ENCRYPTED | The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag. |
| CF_LINK_SUPPRESS_PIN | The profile driver indicates its preference that users not be prompted for a PIN. |
| CFG_ENHANCED | Specifies that the ModeConfig structure is valid. |
| CFG_FCS | Specifies that the Fcs value is valid. |

### -field ConfigOut.Mtu

The range of message transfer units (MTUs) that is used to negotiate the size of the outbound half of channel.

### -field ConfigOut.FlushTO

The range of possible values to be used for the flush timeout for the outbound half of the channel.

### -field ConfigOut.Flow

Reserved for future use. Do not use.

### -field ConfigOut.LinkTO

The Link Manager link timeout.

### -field ConfigOut.NumExtraOptions

The number of array items that are contained in the **ExtraOptions** member. This value should be zero for most clients.

### -field ConfigOut.ExtraOptions

Extra options. This value should be zero for most clients.

### -field ConfigOut.LocalQos

Reserved for future use. Do not use.

### -field ConfigOut.LocalQos.ServiceType

Reserved for future use. Do not use.

### -field ConfigOut.LocalQos.Latency

Reserved for future use. Do not use.

### -field ConfigOut.ModeConfig

Specifies the type of L2CAP channel being opened. This structure is valid only if CFG_ENHANCED flag is specified.

### -field ConfigOut.ModeConfig.Flags

Specifies the type of L2CAP channel mode requested.

| Flag | Description |
| ---- | ----------- |
| CM_BASIC | Open a basic mode channel. |
| CM_RETRANSMISSION_AND_FLOW | Open an enhanced retransmission mode channel. |
| CM_STREAMING | Open a streaming mode channel. |

### -field ConfigOut.ModeConfig.RetransmissionAndFlow

Specifies the options for
CM_RETRANSMISSION_AND_FLOW and CM_STREAMING modes. This structure must be zero if only CM_BASIC is specified in the **Flags** member.

The **Mode** submember of **RetransmissionAndFlow** should be set to 0. Use the **ModeConfig** submember of **RetransmissionAndFlow** to specify the type of channel to open.

### -field ConfigOut.Fcs

Specifies whether FCS should be used for the enhanced L2CAP channel. This value is valid only if CM_RETRANSMISSION_AND_FLOW or CM_STREAMING flag is specified in the **Flags** member.

### -field ConfigOut.ExtendedFlowSpec

Not supported.

### -field ConfigOut.ExtendedWindowSize

Not supported.

### -field ConfigIn

The substructure that contains parameter settings to validate incoming **BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE** BRBs that are sent from a remote device.

### -field ConfigIn.Flags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in the following table:

| Flag | Description |
| ---- | ----------- |
| CF_LINK_AUTHENTICATED | The link must be authenticated. |
| CF_LINK_ENCRYPTED | The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag. |
| CF_LINK_SUPPRESS_PIN | The profile driver indicates its preference that users not be prompted for a PIN. |

### -field ConfigIn.Mtu

The range of message transfer units (MTUs) that is used to negotiate the size of the inbound half of channel.

### -field ConfigIn.FlushTO

The range of possible values to be used for the flush timeout for the inbound half of the channel.

### -field CallbackFlags

A flag that specifies which events should generate a callback routine to notify the profile driver that the event has occurred. Valid flag values are contained in the following table.

| Flag | Description |
| --- | --- |
| CALLBACK_CONFIG_EXTRA_IN | If set, the callback routine will be called when the configuration request for the remote device contains extra options. If not set, the extra configuration options will be rejected as unknown options. This flag is used with **BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE** BRBs. |
| CALLBACK_CONFIG_EXTRA_OUT | If set, the callback routine will be called when the remote device rejects an extra configuration option from a **BRB_L2CA_OPEN_ENHANCED_CHANNEL** request. If not set and the remote device rejects the configuration request due to an extra option, the connection will be closed. |
| CALLBACK_CONFIG_QOS | If set, the callback routine will be called when a remote device sends a configuration request that contains a QOS value. If this flag is not set and the remote device either sends QOS parameters in a configuration request or rejects the profile driver's requested QOS parameters, the connection is disconnected. |
| CALLBACK_DISCONNECT | If set, the callback routine will be called when a remote device disconnects from the enhanced L2CAP channel. |
| CALLBACK_RECV_PACKET | If set, the callback routine will be called when the profile driver receives an incoming enhanced L2CAP packet. |

### -field Callback

The [Enhanced L2CAP Callback Function](./nc-bthddi-pfnbthport_indication_callback_enhanced.md) implemented by the profile driver, that the Bluetooth driver stack should call to notify the profile driver about any changes to the enhanced L2CAP connection.

### -field CallbackContext

The context to pass to the callback function specified in the **Callback** member. The profile driver defines this value.

### -field ReferenceObject

A pointer to an object to pass to [ObReferenceObject](../wdm/nf-wdm-obfreferenceobject.md) and [ObDereferenceObject](../wdm/nf-wdm-obdereferenceobject.md) for which to maintain a reference count.

### -field OutResults

A [CHANNEL_CONFIG_RESULTS_ENHANCED](./ns-bthddi-_channel_config_results_enhanced.md) structure that contains configuration parameters negotiated for the outbound request.

### -field InResults

A CHANNEL_CONFIG_RESULTS_ENHANCED structure that contains configuration parameters negotiated for the inbound request.

### -field IncomingQueueDepth

Specifies the incoming queue length in message transfer units (MTUs).

### -field Reserved

Reserved member. Do not use.

#### - ( unnamed struct )

A [BRB_HEADER](./ns-bthddi-_brb_header.md) structure that contains information about the current BRB.

#### Response

This member is used as an input parameter for a **BRB_L2CA_OPEN_ENHANCED_CHANNEL** request and an output parameter for the **BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE** request.

For a **BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE** request, this member holds a flag that indicates the profile driver's response to the remote device. Valid flag values are contained in the following table.

| Flag | Description |
| ---- | ----------- |
| CONNECT_RSP_RESULT_NO_RESOURCES | The profile driver refused the connection due to a lack of resources. |
| CONNECT_RSP_RESULT_PENDING | The profile driver is currently busy and cannot accept the connection. Try again later. |
| CONNECT_RSP_RESULT_PSM_NEG | The profile driver refused the connection because the PSM is not supported. |
| CONNECT_RSP_RESULT_SECURITY_BLOCK | The profile driver refused the connection for security reasons. |
| CONNECT_RSP_RESULT_SUCCESS | The profile driver accepted the connection. |

For the **BRB_L2CA_OPEN_ENHANCED_CHANNEL** BRB, this member contains the response from the remote device to which the profile driver attempted to connect. Valid flag values are contained in the following table.

|Flag|Description|
|--- |--- |
|CONNECT_RSP_RESULT_NO_RESOURCES|The remote device refused the connection due to a lack of resources.|
|CONNECT_RSP_RESULT_PSM_NEG|The remote device refused the connection.|
|CONNECT_RSP_RESULT_SECURITY_BLOCK|The remote device refused the connection for security reasons.|
|CONNECT_RSP_RESULT_SUCCESS|The remote device accepted the connection.|

#### ResponseStatus

If during a call to the BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE BRB the Response member is set to CONNECT_RSP_RESULT_PENDING, this member is valid and contains one of the following values:

- CONNECT_RSP_STATUS_AUTHENTICATION_PENDING
- CONNECT_RSP_STATUS_AUTHORIZATION_PENDING
- CONNECT_RSP_STATUS_NO_INFORMATION

## -remarks

Profile drivers can use `CM_BASIC | CM_RETRANSMISSION_AND_FLOW`, or `CM_BASIC | CM_STREAMING` modes for the **Flags** member. This indicates to open an enhanced retransmission mode, or streaming mode channel if possible, and if not fall back to basic mode channel. 
A value of `CM_RETRANSMISSION_AND_FLOW | CM_STREAMING` is not supported.