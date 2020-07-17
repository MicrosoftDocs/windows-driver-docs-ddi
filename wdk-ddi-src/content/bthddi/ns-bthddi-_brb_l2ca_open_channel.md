---
UID: NS:bthddi._BRB_L2CA_OPEN_CHANNEL
title: _BRB_L2CA_OPEN_CHANNEL (bthddi.h)
description: The _BRB_L2CA_OPEN_CHANNEL structure describes a L2CAP channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming L2CAP connection request that was initiated by a remote device.
old-location: bltooth\_brb_l2ca_open_channel.htm
tech.root: bltooth
ms.assetid: 16f79360-c8fd-4be9-9c94-7fa2a1d8c6b5
ms.date: 04/27/2018
keywords: ["_BRB_L2CA_OPEN_CHANNEL structure"]
ms.keywords: "_BRB_L2CA_OPEN_CHANNEL, _BRB_L2CA_OPEN_CHANNEL structure [Bluetooth Devices], bltooth._brb_l2ca_open_channel, bth_structs_342ad84f-74fb-481f-b549-8f87c375c4d1.xml, bthddi/_BRB_L2CA_OPEN_CHANNEL"
f1_keywords:
 - "bthddi/_BRB_L2CA_OPEN_CHANNEL"
 - "_BRB_L2CA_OPEN_CHANNEL"
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
- _BRB_L2CA_OPEN_CHANNEL
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_OPEN_CHANNEL structure


## -description


The _BRB_L2CA_OPEN_CHANNEL structure describes a L2CAP channel to open to a remote device, or a
  response from the profile driver accepting or rejecting an incoming L2CAP connection request that was
  initiated by a remote device.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field ChannelHandle



##### 



####### 


### -field Response

 


### -field ResponseStatus

 


### -field Psm

The Protocol/Service Multiplexer (PSM) that the channel uses to connect to the remote device.
      When used with a <b>BRB_L2CA_OPEN_CHANNEL</b> request, this member is set as an input field. When used with a
      <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request, this member is used as an output field.


### -field ChannelFlags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in
     the following table:
     

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field BtAddress

The Bluetooth address of the device for which the connection is intended.


### -field ConfigOut

The substructure that contains parameter settings for a <b>BRB_L2CA_OPEN_CHANNEL</b> BRB sent to a remote
     device.


### -field ConfigOut.Flags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in
      the following table:
      

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field ConfigOut.Mtu

The range of message transfer units (MTUs) that is used to negotiate the size of the outbound
      half of channel.


### -field ConfigOut.FlushTO

The range of possible values to be used for the flush timeout for the outbound half of the
      channel.


### -field ConfigOut.Flow

Reserved for future use. Do not use.


### -field ConfigOut.LinkTO

The Link Manager link timeout.


### -field ConfigOut.NumExtraOptions

The number of array items that are contained in the 
      <b>ExtraOptions</b> member. This value should be zero for most clients.


### -field ConfigOut.ExtraOptions

The number of array items that are contained in the 
      <b>ExtraOptions</b> member. This value should be zero for most clients.


### -field ConfigOut.LocalQos

Reserved for future use. Do not use.


### -field ConfigOut.LocalQos.ServiceType

Reserved for future use. Do not use.


### -field ConfigOut.LocalQos.Latency

Reserved for future use. Do not use.


### -field ConfigIn

The substructure that contains parameter settings to validate incoming
     <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRBs that are sent from a remote device.


### -field ConfigIn.Flags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in
      the following table:
      

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field ConfigIn.Mtu

The range of message transfer units (MTUs) that is used to negotiate the size of the outbound
      half of channel.


### -field ConfigIn.FlushTO

The range of possible values to be used for the flush timeout for the outbound half of the
      channel.


### -field CallbackFlags

A flag that specifies which events should generate a callback routine to notify the profile driver
     that the event has occurred. Valid flag values are contained in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CALLBACK_CONFIG_EXTRA_IN

</td>
<td>
If set, the callback routine will be called when the configuration request for the remote device
        contains extra options. If not set, the extra configuration options will be rejected as unknown
        options. This flag is used with <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRBs.

</td>
</tr>
<tr>
<td>
CALLBACK_CONFIG_EXTRA_OUT

</td>
<td>
If set, the callback routine will be called when the remote device rejects an extra configuration
        option from a <b>BRB_L2CA_OPEN_CHANNEL</b> request. If not set and the remote device rejects the
        configuration request due to an extra option, the connection will be closed.

</td>
</tr>
<tr>
<td>
CALLBACK_CONFIG_QOS

</td>
<td>
If set, the callback routine will be called when a remote device sends a configuration request
        that contains a QOS value. If this flag is not set and the remote device either sends QOS parameters
        in a configuration request or rejects the profile driver's requested QOS parameters, the connection
        is disconnected.

</td>
</tr>
<tr>
<td>
CALLBACK_DISCONNECT

</td>
<td>
If set, the callback routine will be called when a remote device disconnects from the L2CAP
        channel.

</td>
</tr>
<tr>
<td>
CALLBACK_RECV_PACKET

</td>
<td>
If set, the callback routine will be called when the profile driver receives an incoming L2CAP
        packet.

</td>
</tr>
</table>
 


### -field Callback

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback
     Function</a> implemented by the profile driver, that the Bluetooth driver stack should call to notify
     the profile driver about any changes to the L2CAP connection.


### -field CallbackContext

The context to pass to the callback function specified in the 
     <b>Callback</b> member. The profile driver defines this value.


### -field ReferenceObject

A pointer to an object to pass to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a> and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> for which to
     maintain a reference count of.


### -field OutResults

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_channel_config_results">CHANNEL_CONFIG_RESULTS</a> structure that
     contains configuration parameters for the outbound request.


### -field InResults

A CHANNEL_CONFIG_RESULTS structure that contains configuration parameters for the inbound
     request.


### -field IncomingQueueDepth

Specifies the incoming queue length in message transfer units (MTUs).


#### - ( unnamed struct )

A 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
      about the current BRB.



#### Response

This member is used as an input parameter for a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request and an
       output parameter for the <b>BRB_L2CA_OPEN_CHANNEL</b> request.
       

For a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request, this member holds a flag that indicates the profile
       driver's response to the remote device. Valid flag values are contained in the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_NO_RESOURCES

</td>
<td>
The profile driver refused the connection due to a lack of resources.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_PENDING

</td>
<td>
The profile driver is currently busy and cannot accept the connection. Try again later.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_PSM_NEG

</td>
<td>
The profile driver refused the connection because the PSM is not supported.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SECURITY_BLOCK

</td>
<td>
The profile driver refused the connection for security reasons.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SUCCESS

</td>
<td>
The profile driver accepted the connection.

</td>
</tr>
</table>
 

For the <b>BRB_L2CA_OPEN_CHANNEL</b> BRB, this member contains the response from the remote device to
       which the profile driver attempted to connect. Valid flag values are contained in the following
       table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_NO_RESOURCES

</td>
<td>
The remote device refused the connection due to a lack of resources.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_PSM_NEG

</td>
<td>
The remote device refused the connection.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SECURITY_BLOCK

</td>
<td>
The remote device refused the connection for security reasons.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SUCCESS

</td>
<td>
The remote device accepted the connection.

</td>
</tr>
</table>
 



#### ResponseStatus



##### If during a call to the BRB_L2CA_OPEN_CHANNEL_RESPONSE BRB the 
       Response member is set to CONNECT_RSP_RESULT_PENDING, this member is valid and contains one of
       the following values:



##### CONNECT_RSP_STATUS_AUTHENTICATION_PENDING



##### CONNECT_RSP_STATUS_AUTHORIZATION_PENDING



##### CONNECT_RSP_STATUS_NO_INFORMATION


## -remarks



To open a L2CAP channel, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a> request.

Profile drivers that act as clients specify a destination address, a PSM, and a variety of
    configuration parameters.

If the <b>BRB_L2CA_OPEN_CHANNEL</b> request completes successfully, a variety of information about the newly
    created connection is available in the 
    <b>OutResults</b> and 
    <b>InResults</b> members. 
    <b>OutResults</b> specifies the parameters for the outbound half of the channel, and 
    <b>InResults</b> specifies the parameters for the inbound half of the channel.

Several of the configuration parameters passed in this structure, such as the 
    <b>Mtu</b> member, are ranges used for negotiation with the remote radio. Clients should provide as wide a
    range as possible to increase the chances of successful channel negotiation. Specifying a minimum MTU
    size greater than the basic Bluetooth minimum MTU size should only be done when absolutely necessary. If
    negotiation fails, the connection will fail.

Profile drivers must allocate the memory to store the array that is stored in the 
    <b>ExtraOptions</b> member and should not free this memory until the callback function defined in the 
    <b>Callback</b> member returns with an 
    <b>IndicationFreeExtraOptions</b> notification 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_indication_code">INDICATION_CODE</a> value passed in its 
    <i>Indication</i> parameter.

The 
    <b>IncomingQueueDepth</b> member of the _BRB_L2CA_OPEN_CHANNEL structure specifies the maximum number of
    MTUs that the Bluetooth driver stack will receive and queue on the connection before it begins to discard
    them. Setting this value to a very small number increases the chances of data loss, while setting it to a
    very large number can increase memory usage. Setting this member to 10 is an effective compromise.

To accept or reject an incoming L2CAP connection request initiated by a remote device, profile drivers
    should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536616(v=vs.85)">
    BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.

A profile driver should build and send a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request when the Bluetooth
    driver stack calls the profile driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a> and passes 
    <b>IndicationRemoteConnect</b> in the callback function's 
    <i>Indication</i> parameter.

Based on the value of the 
    <b>Response</b> member of this structure, the Bluetooth driver stack will then accept or reject the
    connection request.

The profile driver specifies whether the connection should be accepted by storing an appropriate value
    in the 
    <b>Response</b> member of this structure.

Upon receiving the CONNECT_RSP_RESULT_PENDING response, the connecting client should reset its
    connection timer and wait for an updated connection response message. Profile drivers calling the
    <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRB where the 
    <b>Response</b> member is set to CONNECT_RSP_RESULT_PENDING should promptly issue an additional
    <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRB with an updated connection value. The updated value can be any of the
    status codes described in the 
    <b>Response</b> member, including resending a CONNECT_RSP_RESULT_PENDING value.

Profile drivers must allocate the memory to store the array that is stored in the 
    <b>ExtraOptions</b> member and should not free this memory until the callback function that is defined in
    the 
    <b>Callback</b> member returns with an 
    <b>IndicationFreeExtraOptions</b> notification 
    <b>INDICATION_CODE</b> value passed in its 
    <i>Indication</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a>



<a href="https://docs.microsoft.com/previous-versions/ff536616(v=vs.85)">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>



<a href="https://docs.microsoft.com/previous-versions/ff536618(v=vs.85)">BRB_L2CA_REGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_channel_config_results">CHANNEL_CONFIG_RESULTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_indication_code">INDICATION_CODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbthport_indication_callback">L2CAP Callback Function</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_l2cap_config_option">L2CAP_CONFIG_OPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a>
 

 

