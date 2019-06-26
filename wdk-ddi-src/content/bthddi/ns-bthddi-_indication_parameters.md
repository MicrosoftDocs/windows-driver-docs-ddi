---
UID: NS:bthddi._INDICATION_PARAMETERS
title: _INDICATION_PARAMETERS (bthddi.h)
description: The INDICATION_PARAMETERS structure is passed as the Parameters parameter to a profile driver's L2CAP Callback Function.
old-location: bltooth\indication_parameters.htm
tech.root: bltooth
ms.assetid: fc93ab8a-01d2-4827-8d89-06f09bf10456
ms.date: 04/27/2018
ms.keywords: "*PINDICATION_PARAMETERS, INDICATION_PARAMETERS, INDICATION_PARAMETERS structure [Bluetooth Devices], PINDICATION_PARAMETERS, PINDICATION_PARAMETERS structure pointer [Bluetooth Devices], _INDICATION_PARAMETERS, bltooth.indication_parameters, bth_structs_8cf076cf-a280-49ee-bbe6-cc54e854905e.xml, bthddi/INDICATION_PARAMETERS, bthddi/PINDICATION_PARAMETERS"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthddi.h
api_name:
- INDICATION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: "*PINDICATION_PARAMETERS, INDICATION_PARAMETERS"
---

# _INDICATION_PARAMETERS structure


## -description


The INDICATION_PARAMETERS structure is passed as the 
  <i>Parameters</i> parameter to a profile driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a>.


## -struct-fields




### -field ConnectionHandle

The L2CAP connection handle to the remote device. This handle is only valid for notifications that
     arrive over an established L2CAP connection.


### -field BtAddress

The Bluetooth address of the remote device.


### -field Parameters


### -field Parameters.Connect

The structure that contains parameters for the 
      <b>IndicationRemoteConnect</b> callback function.


### -field Parameters.Connect.Request

The structure that contains the parameters for a connection request.


### -field Parameters.Connect.Request.PSM

The Protocol/Service Multiplexer (PSM) that is passed to the calling function when the 
        <b>IndicationRemoteConnectINDICATION_CODE</b> value is specified in the callback function's 
        <i>Indication</i> parameter.


### -field Parameters.ConfigRequest

The structure that contains parameters for the 
      <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.


### -field Parameters.ConfigRequest.CurrentParams

A 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_channel_config_parameters">
       CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.


### -field Parameters.ConfigRequest.RequestedParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.


### -field Parameters.ConfigRequest.ResponseParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that the profile driver
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
The configuration request failed because the L2CAP connection was disconnected.

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
      <b>IndicationRemoteConfigResponseINDICATION_CODE</b> value.


### -field Parameters.ConfigResponse.CurrentParams

A 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_channel_config_parameters">
       CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.


### -field Parameters.ConfigResponse.RequestedParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.


### -field Parameters.ConfigResponse.RejectedParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the configuration parameter settings that
       were rejected by the remote device.


### -field Parameters.ConfigResponse.UnknownTypes

An array of types that were not recognized by the responding device.


### -field Parameters.ConfigResponse.NumUnknownTypes

The number of unrecognized types in the 
       <b>UnknownTypes</b> member.


### -field Parameters.ConfigResponse.NewRequestParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameter settings for the callback
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
The configuration request failed because the L2CAP connection was disconnected.

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
      <b>IndicationFreeExtraOptionsINDICATION_CODE</b> value.


### -field Parameters.FreeExtraOptions.NumExtraOptions

The number of extra options contained in the 
       <b>ExtraOptions</b> member.


### -field Parameters.FreeExtraOptions.ExtraOptions

The number of extra options contained in the 
       <b>ExtraOptions</b> member.


### -field Parameters.Disconnect

The structure that contains the parameters for the 
      <b>IndicationRemoteDisconnectINDICATION_CODE</b> value.


### -field Parameters.Disconnect.Reason

An 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ne-bthddi-_l2cap_disconnect_reason">L2CAP_DISCONNECT_REASON</a> value that
       indicates why the L2CAP connection to the remote device was terminated.


### -field Parameters.Disconnect.CloseNow

A Boolean value that a profile driver uses to notify the Bluetooth driver stack to close the
       L2CAP connection. Set this member to <b>TRUE</b> to notify the Bluetooth driver stack to close the
       connection. Otherwise, set it to <b>FALSE</b> to keep the connection open.


### -field Parameters.RecvPacket

The structure that contains the parameters for the 
      <b>IndicationRecvPacketINDICATION_CODE</b> value.


### -field Parameters.RecvPacket.PacketLength

The size, in bytes, of the packet that the callback function sent over the L2CAP
       connection.


### -field Parameters.RecvPacket.TotalQueueLength

The number of packets to be processed over the L2CAP connection.


## -remarks



A profile driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a> should
    process this structure differently depending upon the value that the Bluetooth driver stack passes in the
    
    <i>Indication</i> parameter of the callback function.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteConnect</b>, the callback function should use the 
    <b>Connect</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteDisconnect</b>, the callback function should use the 
    <b>Disconnect</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteConfigRequest</b>, the callback function should use the 
    <b>ConfigRequest</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteConfigResponse</b>, the callback function should use the 
    <b>ConfigResponse</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteFreeExtraOptions</b>, the callback function should use the 
    <b>FreeExtraOptions</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteRecvPacket</b>, the callback function should use the 
    <b>RecvPacket</b> member of the 
    <b>Parameters</b> union.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_channel_config_parameters">CHANNEL_CONFIG_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ne-bthddi-_indication_code">INDICATION_CODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_l2cap_config_option">L2CAP_CONFIG_OPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ne-bthddi-_l2cap_disconnect_reason">L2CAP_DISCONNECT_REASON</a>
 

 

