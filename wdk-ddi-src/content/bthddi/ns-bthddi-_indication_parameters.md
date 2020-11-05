---
UID: NS:bthddi._INDICATION_PARAMETERS
title: _INDICATION_PARAMETERS (bthddi.h)
description: The INDICATION_PARAMETERS structure is passed as the Parameters parameter to a profile driver's L2CAP Callback Function.
old-location: bltooth\indication_parameters.htm
tech.root: bltooth
ms.assetid: fc93ab8a-01d2-4827-8d89-06f09bf10456
ms.date: 10/16/2020
keywords: ["INDICATION_PARAMETERS structure"]
ms.keywords: "*PINDICATION_PARAMETERS, INDICATION_PARAMETERS, INDICATION_PARAMETERS structure [Bluetooth Devices], PINDICATION_PARAMETERS, PINDICATION_PARAMETERS structure pointer [Bluetooth Devices], _INDICATION_PARAMETERS, bltooth.indication_parameters, bth_structs_8cf076cf-a280-49ee-bbe6-cc54e854905e.xml, bthddi/INDICATION_PARAMETERS, bthddi/PINDICATION_PARAMETERS"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.typenames: "*PINDICATION_PARAMETERS, INDICATION_PARAMETERS"
f1_keywords:
 - _INDICATION_PARAMETERS
 - bthddi/_INDICATION_PARAMETERS
 - PINDICATION_PARAMETERS
 - bthddi/PINDICATION_PARAMETERS
 - INDICATION_PARAMETERS
 - bthddi/INDICATION_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - INDICATION_PARAMETERS
---

# _INDICATION_PARAMETERS structure

## -description

The **INDICATION_PARAMETERS** structure is passed as the *Parameters* parameter to a profile driver's [L2CAP Callback Function](./nc-bthddi-pfnbthport_indication_callback.md)

## -struct-fields

### -field ConnectionHandle

The L2CAP connection handle to the remote device. This handle is only valid for notifications that arrive over an established L2CAP connection.

### -field BtAddress

The Bluetooth address of the remote device.

### -field Parameters

### -field Parameters.Connect

The structure that contains parameters for the **IndicationRemoteConnect** callback function.

### -field Parameters.Connect.Request

The structure that contains the parameters for a connection request.

### -field Parameters.Connect.Request.PSM

The Protocol/Service Multiplexer (PSM) that is passed to the calling function when the **IndicationRemoteConnectINDICATION_CODE** value is specified in the callback function's *Indication* parameter.

### -field Parameters.ConfigRequest

The structure that contains parameters for the **IndicationRemoteConfigRequestINDICATION_CODE** value.

### -field Parameters.ConfigRequest.CurrentParams

A [CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the parameters for the current channel. This value is only valid if the channel was previously open and is now in the process of being configured. This member is used when the callback function specifies the   **IndicationRemoteConfigRequestINDICATION_CODE** value.

### -field Parameters.ConfigRequest.RequestedParams

A [CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the parameters that are passed from the remote host for configuration requests. This member is used when the callback function specifies the **IndicationRemoteConfigRequestINDICATION_CODE** value.

### -field Parameters.ConfigRequest.ResponseParams

A [CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the parameters that the profile driver responds to the configuration request with.

### -field Parameters.ConfigRequest.Response

A flag that indicates the status of the configuration request. Valid flag values are listed in the following table.

| Flag | Description |
| --- | --- |
| CONFIG_STATUS_SUCCESS | The configuration request was successful. |
| CONFIG_STATUS_DISCONNECT | The configuration request failed because the L2CAP connection was disconnected. |
| CONFIG_STATUS_INVALID_PARAMETER | The configuration request failed because an invalid parameter was passed to the profile driver. |
| CONFIG_STATUS_REJECT | The profile driver rejected the configuration request. |
| CONFIG_STATUS_UNKNOWN_OPTION |The configuration request failed because one of the specified configuration options was not recognized by the profile driver. |

### -field Parameters.ConfigResponse

The structure that contains parameters for the **IndicationRemoteConfigResponseINDICATION_CODE** value.

### -field Parameters.ConfigResponse.CurrentParams

A [CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the parameters for the current channel. This value is only valid if the channel was previously open and is now in the process of being configured. This member is used when the callback function specifies the **IndicationRemoteConfigRequestINDICATION_CODE** value.

### -field Parameters.ConfigResponse.RequestedParams

A [CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the parameters that are passed from the remote host for configuration requests. This member is used when the callback function specifies the **IndicationRemoteConfigRequestINDICATION_CODE** value.

### -field Parameters.ConfigResponse.RejectedParams

A *[CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the configuration parameter settings that were rejected by the remote device.

### -field Parameters.ConfigResponse.UnknownTypes

An array of types that were not recognized by the responding device.

### -field Parameters.ConfigResponse.NumUnknownTypes

The number of unrecognized types in the **UnknownTypes** member.

### -field Parameters.ConfigResponse.NewRequestParams

A *[CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md) structure that contains the parameter settings for the callback function to resubmit after the response has returned from the remote device.

### -field Parameters.ConfigResponse.Response

A flag that indicates the status of the configuration request. Valid flag values are listed in the following table.

| Flag | Description |
| --- | --- |
| CONFIG_STATUS_SUCCESS | The configuration request was successful. |
| CONFIG_STATUS_DISCONNECT | The configuration request failed because the L2CAP connection was disconnected. |
| CONFIG_STATUS_INVALID_PARAMETER | The configuration request failed because an invalid parameter was passed to the profile driver. |
| CONFIG_STATUS_REJECT | The profile driver rejected the configuration request. |
| CONFIG_STATUS_UNKNOWN_OPTION | The configuration request failed because one of the specified configuration options was not recognized by the profile driver. |

### -field Parameters.FreeExtraOptions

The structure that contains parameters for the **IndicationFreeExtraOptionsINDICATION_CODE** value.

### -field Parameters.FreeExtraOptions.NumExtraOptions

The number of extra options contained in the **ExtraOptions** member.

### -field Parameters.FreeExtraOptions.ExtraOptions

The number of extra options contained in the **ExtraOptions** member.

### -field Parameters.Disconnect

The structure that contains the parameters for the **IndicationRemoteDisconnectINDICATION_CODE** value.

### -field Parameters.Disconnect.Reason

An [L2CAP_DISCONNECT_REASON](./ne-bthddi-_l2cap_disconnect_reason.md) value that indicates why the L2CAP connection to the remote device was terminated.

### -field Parameters.Disconnect.CloseNow

A Boolean value that a profile driver uses to notify the Bluetooth driver stack to close the L2CAP connection. Set this member to **TRUE** to notify the Bluetooth driver stack to close the connection. Otherwise, set it to **FALSE** to keep the connection open.

### -field Parameters.RecvPacket

The structure that contains the parameters for the **IndicationRecvPacketINDICATION_CODE** value.

### -field Parameters.RecvPacket.PacketLength

The size, in bytes, of the packet that the callback function sent over the L2CAP connection.

### -field Parameters.RecvPacket.TotalQueueLength

The number of packets to be processed over the L2CAP connection.

## -remarks

A profile driver's [L2CAP Callback Function](./nc-bthddi-pfnbthport_indication_callback.md) should process this structure differently depending upon the value that the Bluetooth driver stack passes in the *Indication* parameter of the callback function.

- When the Bluetooth driver stack passes **IndicationRemoteConnect**, the callback function should use the **Connect** member of the **Parameters** union.

- When the Bluetooth driver stack passes **IndicationRemoteDisconnect**, the callback function should use the **Disconnect** member of the **Parameters** union.

- When the Bluetooth driver stack passes **IndicationRemoteConfigRequest**, the callback function should use the **ConfigRequest** member of the **Parameters** union.

- When the Bluetooth driver stack passes **IndicationRemoteConfigResponse**, the callback function should use the **ConfigResponse** member of the **Parameters** union.

- When the Bluetooth driver stack passes **IndicationRemoteFreeExtraOptions**, the callback function should use the **FreeExtraOptions** member of the **Parameters** union.

- When the Bluetooth driver stack passes **IndicationRemoteRecvPacket**, the callback function should use the **RecvPacket** member of the **Parameters** union.

## -see-also

[CHANNEL_CONFIG_PARAMETERS](./ns-bthddi-_channel_config_parameters.md)

[INDICATION_CODE](./ne-bthddi-_indication_code.md)

[L2CAP Callback Function](./nc-bthddi-pfnbthport_indication_callback.md)

[L2CAP_CONFIG_OPTION](./ns-bthddi-_l2cap_config_option.md)

[L2CAP_DISCONNECT_REASON](./ne-bthddi-_l2cap_disconnect_reason.md)