---
UID: NS:bthddi._INDICATION_PARAMETERS_ENHANCED
title: _INDICATION_PARAMETERS_ENHANCED (bthddi.h)
description: The INDICATION_PARAMETERS_ENHANCED structure is passed as the Parameters parameter to a profile driver's enhanced L2CAP Callback Function.
old-location: bltooth\indication_parameters_enhanced.htm
tech.root: bltooth
ms.assetid: D0FBA555-B61F-4D6F-B93F-C77D395F2BCD
ms.date: 04/27/2018
ms.keywords: "*PINDICATION_PARAMETERS_ENHANCED, INDICATION_PARAMETERS_ENHANCED, INDICATION_PARAMETERS_ENHANCED structure [Bluetooth Devices], PINDICATION_PARAMETERS_ENHANCED, PINDICATION_PARAMETERS_ENHANCED structure pointer [Bluetooth Devices], _INDICATION_PARAMETERS_ENHANCED, bltooth.indication_parameters_enhanced, bthddi/INDICATION_PARAMETERS_ENHANCED, bthddi/PINDICATION_PARAMETERS_ENHANCED"
f1_keywords:
 - "bthddi/INDICATION_PARAMETERS_ENHANCED"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthddi.h
api_name:
- INDICATION_PARAMETERS_ENHANCED
product:
- Windows
targetos: Windows
req.typenames: "*PINDICATION_PARAMETERS_ENHANCED, INDICATION_PARAMETERS_ENHANCED"
---

# _INDICATION_PARAMETERS_ENHANCED structure


## -description


The INDICATION_PARAMETERS_ENHANCED structure is passed as the Parameters parameter to a profile driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbthport_indication_callback_enhanced">enhanced L2CAP Callback Function</a>



## -struct-fields




### -field ConnectionHandle

The L2CAP connection handle to the remote device. This handle is only valid for notifications that
     arrive over an established L2CAP connection.


### -field BtAddress

The Bluetooth address of the remote device.


### -field Parameters


### -field Parameters.Connect

The structure that contains parameters for the 
      <i>IndicationRemoteConnect</i> callback function.


### -field Parameters.Connect.Request

The structure that contains the parameters for a connection request.


### -field Parameters.Connect.Request.PSM

The Protocol/Service Multiplexer (PSM) that is passed to the calling function when the 
        <i>IndicationRemoteConnect</i> INDICATION_CODE value is specified in the enhanced callback function's 
        <i>Indication</i> parameter.


### -field Parameters.ConfigRequest

The structure that contains parameters for the 
      <i>IndicationRemoteConfigRequest</i> INDICATION_CODE value.


### -field Parameters.ConfigRequest.CurrentParams

A 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_channel_config_parameters_enhanced">CHANNEL_CONFIG_PARAMETERS_ENHANCED</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <i>IndicationRemoteConfigRequest</i> INDICATION_CODE value.


### -field Parameters.ConfigRequest.RequestedParams

A CHANNEL_CONFIG_PARAMETERS_ENHANCED structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <i>IndicationRemoteConfigRequest</i> INDICATION_CODE value.


### -field Parameters.ConfigRequest.ResponseParams

A CHANNEL_CONFIG_PARAMETERS_ENHANCED structure that contains the parameters that the profile driver
       responds to the configuration request with.


### -field Parameters.ConfigRequest.Response

A flag that indicates the status of the configuration request. Valid flag values are listed in
       the following table.
       

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONFIG_STATUS_SUCCESS

</td>
<td>
The configuration request was successful.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_DISCONNECT

</td>
<td>
The configuration request failed because the enhanced L2CAP connection was disconnected.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_INVALID_PARAMETER

</td>
<td>
The configuration request failed because an invalid parameter was passed to the profile
          driver.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_REJECT

</td>
<td>
The profile driver rejected the configuration request.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_UNKNOWN_OPTION

</td>
<td>
The configuration request failed because one of the specified configuration options was not
          recognized by the profile driver.

</td>
</tr>
</table>
 


### -field Parameters.ConfigResponse

The structure that contains parameters for the 
      <i>IndicationRemoteConfigResponse</i> INDICATION_CODE value.


### -field Parameters.ConfigResponse.CurrentParams

A 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_channel_config_parameters_enhanced">CHANNEL_CONFIG_PARAMETERS_ENHANCED</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <i>IndicationRemoteConfigRequest</i> INDICATION_CODE value.


### -field Parameters.ConfigResponse.RequestedParams

A CHANNEL_CONFIG_PARAMETERS_ENHANCED structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <i>IndicationRemoteConfigRequest</i> INDICATION_CODE value.


### -field Parameters.ConfigResponse.RejectedParams

A CHANNEL_CONFIG_PARAMETERS_ENHANCED structure that contains the configuration parameter settings that
       were rejected by the remote device.


### -field Parameters.ConfigResponse.UnknownTypes

An array of types that were not recognized by the responding device.


### -field Parameters.ConfigResponse.NumUnknownTypes

The number of unrecognized types in the 
       <b>UnknownTypes</b> member.


### -field Parameters.ConfigResponse.NewRequestParams

A CHANNEL_CONFIG_PARAMETERS_ENHANCED structure that contains the parameter settings for the enhanced callback
       function to resubmit after the response has returned from the remote device.


### -field Parameters.ConfigResponse.Response

A flag that indicates the status of the configuration request. Valid flag values are listed in
       the following table.
       

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONFIG_STATUS_SUCCESS

</td>
<td>
The configuration request was successful.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_DISCONNECT

</td>
<td>
The configuration request failed because the enhanced L2CAP connection was disconnected.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_INVALID_PARAMETER

</td>
<td>
The configuration request failed because an invalid parameter was passed to the profile
          driver.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_REJECT

</td>
<td>
The profile driver rejected the configuration request.

</td>
</tr>
<tr>
<td>
CONFIG_STATUS_UNKNOWN_OPTION

</td>
<td>
The configuration request failed because one of the specified configuration options was not
          recognized by the profile driver.

</td>
</tr>
</table>
 


### -field Parameters.FreeExtraOptions

The structure that contains parameters for the 
      <i>IndicationFreeExtraOptions</i> INDICATION_CODE value.


### -field Parameters.FreeExtraOptions.NumExtraOptions

The number of extra options contained in the 
       <b>ExtraOptions</b> member.


### -field Parameters.FreeExtraOptions.ExtraOptions

Extra options.


### -field Parameters.Disconnect

The structure that contains the parameters for the 
      <i>IndicationRemoteDisconnect</i> INDICATION_CODE value.


### -field Parameters.Disconnect.Reason

An 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_l2cap_disconnect_reason">L2CAP_DISCONNECT_REASON</a> value that
       indicates why the L2CAP connection to the remote device was terminated.


### -field Parameters.Disconnect.CloseNow

A Boolean value that a profile driver uses to notify the Bluetooth driver stack to close the
       L2CAP connection. Set this member to <b>TRUE</b> to notify the Bluetooth driver stack to close the
       connection. Otherwise, set it to <b>FALSE</b> to keep the connection open.


### -field Parameters.RecvPacket

The structure that contains the parameters for the 
      <i>IndicationRecvPacket</i> INDICATION_CODE value.


### -field Parameters.RecvPacket.PacketLength

The size, in bytes, of the packet that the callback function sent over the L2CAP
       connection.


### -field Parameters.RecvPacket.TotalQueueLength

The number of packets to be processed over the L2CAP connection.


### -field Parameters.Reserved

Reserved member. Do not use.

