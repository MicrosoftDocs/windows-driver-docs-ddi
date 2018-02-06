---
UID: NS:bthddi._BRB_L2CA_OPEN_ENHANCED_CHANNEL
title: "_BRB_L2CA_OPEN_ENHANCED_CHANNEL"
author: windows-driver-content
description: The _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure is used to open an enhanced L2CAP channel to a remote device, or send a response for accepting/rejecting an incoming enhanced L2CAP connection request that was initiated by a remote device.
old-location: bltooth\_brb_l2ca_open_enhanced_channel.htm
old-project: bltooth
ms.assetid: 34CA2A3E-871F-46D4-962A-8EE8D7B8DA15
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: BRB_L2CA_OPEN_ENHANCED_CHANNEL structure [Bluetooth Devices], bltooth.brb_l2ca_open_enhanced_channel, bthddi/PBRB_L2CA_OPEN_ENHANCED_CHANNEL, PBRB_L2CA_OPEN_ENHANCED_CHANNEL, bthddi/_BRB_L2CA_OPEN_ENHANCED_CHANNEL, _BRB_L2CA_OPEN_ENHANCED_CHANNEL, bltooth._brb_l2ca_open_enhanced_channel, BRB_L2CA_OPEN_ENHANCED_CHANNEL, _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure [Bluetooth Devices], PBRB_L2CA_OPEN_ENHANCED_CHANNEL structure pointer [Bluetooth Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthddi.h
apiname:
-	BRB_L2CA_OPEN_ENHANCED_CHANNEL
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure


## -description


The _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure is used to open an enhanced L2CAP channel to a remote device, or send a response for accepting/rejecting an incoming enhanced L2CAP connection request that was initiated by a remote device.


## -syntax


````
typedef struct _BRB_L2CA_OPEN_ENHANCED_CHANNEL {
  BRB_HEADER                              Hdr;
  L2CAP_CHANNEL_HANDLE                    ChannelHandle;
  union {
    struct {
      USHORT Response;
      USHORT ResponseStatus;
    };
    USHORT Psm;
  };
  ULONG                                   ChannelFlags;
  BTH_ADDR                                BtAddress;
  struct {
    ULONG                    Flags;
    L2CAP_CONFIG_VALUE_RANGE Mtu;
    L2CAP_CONFIG_VALUE_RANGE FlushTO;
    L2CAP_FLOWSPEC           Flow;
    USHORT                   LinkTO;
    ULONG                    NumExtraOptions;
    PL2CAP_CONFIG_OPTION     ExtraOptions;
    struct {
      UCHAR ServiceType;
      ULONG Latency;
    } LocalQos;
    struct {
      ULONG                                 Flags;
      L2CAP_RETRANSMISSION_AND_FLOW_CONTROL RetransmissionAndFlow;
    } ModeConfig;
    USHORT                   Fcs;
    L2CAP_EXTENDED_FLOW_SPEC ExtendedFlowSpec;
    USHORT                   ExtendedWindowSize;
  } ConfigOut;
  struct {
    ULONG                    Flags;
    L2CAP_CONFIG_VALUE_RANGE Mtu;
    L2CAP_CONFIG_RANGE       FlushTO;
  } ConfigIn;
  ULONG                                   CallbackFlags;
  PFNBTHPORT_INDICATION_CALLBACK_ENHANCED Callback;
  PVOID                                   CallbackContext;
  PVOID                                   ReferenceObject;
  CHANNEL_CONFIG_RESULTS_ENHANCED         OutResults;
  CHANNEL_CONFIG_RESULTS_ENHANCED         InResults;
  UCHAR                                   IncomingQueueDepth;
  PVOID                                   Reserved;
} BRB_L2CA_OPEN_ENHANCED_CHANNEL, *PBRB_L2CA_OPEN_ENHANCED_CHANNEL;
````


## -struct-fields




### -field ConfigOut

The substructure that contains parameter settings for a <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL</b> BRB sent to a remote
     device.


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
CM_BASIC

</td>
<td>
Open a basic mode channel.

</td>
</tr>
<tr>
<td>
CM_RETRANSMISSION_AND_FLOW

</td>
<td>
Open an enhanced retransmission mode channel.

</td>
</tr>
<tr>
<td>
CM_STREAMING

</td>
<td>
Open a streaming mode channel.

</td>
</tr>
</table> 


### -field ConfigOut.ModeConfig.RetransmissionAndFlow

Specifies the options for
CM_RETRANSMISSION_AND_FLOW and CM_STREAMING modes. This structure must be zero if only CM_BASIC is specified in the <b>Flags</b> member.

The <b>Mode</b> submember of <b>RetransmissionAndFlow</b> should be set to 0. Use the <b>ModeConfig</b> submember of <b>RetransmissionAndFlow</b> to specify the type of channel to open.


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
<tr>
<td>
CFG_ENHANCED

</td>
<td>
Specifies that the ModeConfig structure is valid.

</td>
</tr>
<tr>
<td>
CFG_FCS

</td>
<td>
Specifies that the Fcs value is valid.

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

Extra options. This value should be zero for most clients.


### -field ConfigOut.Fcs

Specifies whether FCS should be used for the enhanced L2CAP channel. This value is valid only if CM_RETRANSMISSION_AND_FLOW or CM_STREAMING flag is specified in the <b>Flags</b> member.


### -field ConfigOut.ExtendedFlowSpec

Not supported.


### -field ConfigOut.ExtendedWindowSize

Not supported.


### -field ConfigIn

The substructure that contains parameter settings to validate incoming
     <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE</b> BRBs that are sent from a remote device.


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

The range of message transfer units (MTUs) that is used to negotiate the size of the inbound
      half of channel.


### -field ConfigIn.FlushTO

The range of possible values to be used for the flush timeout for the inbound half of the
      channel.


### -field Response

 


### -field ResponseStatus

 


### -field Psm

The Protocol/Service Multiplexer (PSM) that the channel uses to connect to the remote device.
      When used with a <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL</b> request, this member is set as an input field. When used with a
      <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE</b> request, this member is used as an output field.


### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field ChannelHandle



#### 



#### 



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
        options. This flag is used with <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE</b> BRBs.

</td>
</tr>
<tr>
<td>
CALLBACK_CONFIG_EXTRA_OUT

</td>
<td>
If set, the callback routine will be called when the remote device rejects an extra configuration
        option from a <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL</b> request. If not set and the remote device rejects the
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
If set, the callback routine will be called when a remote device disconnects from the enhanced L2CAP
        channel.

</td>
</tr>
<tr>
<td>
CALLBACK_RECV_PACKET

</td>
<td>
If set, the callback routine will be called when the profile driver receives an incoming enhanced L2CAP
        packet.

</td>
</tr>
</table> 


### -field Callback

The 
     <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback_enhanced.md">Enhanced L2CAP Callback
     Function</a> implemented by the profile driver, that the Bluetooth driver stack should call to notify
     the profile driver about any changes to the enhanced L2CAP connection.


### -field CallbackContext

The context to pass to the callback function specified in the 
     <b>Callback</b> member. The profile driver defines this value.


### -field ReferenceObject

A pointer to an object to pass to 
     <a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a> and 
     <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> for which to
     maintain a reference count of.


### -field OutResults

A 
     <a href="..\bthddi\ns-bthddi-_channel_config_results_enhanced.md">CHANNEL_CONFIG_RESULTS_ENHANCED</a> structure that
     contains configuration parameters negotiated for the outbound request.


### -field InResults

A CHANNEL_CONFIG_RESULTS_ENHANCED structure that contains configuration parameters negotiated for the inbound
     request.


### -field IncomingQueueDepth

Specifies the incoming queue length in message transfer units (MTUs).


### -field Reserved

Reserved member. Do not use.


#### - ( unnamed struct )

A 
      <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
      about the current BRB.


#### Response

This member is used as an input parameter for a <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL</b> request and an
       output parameter for the <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE</b> request.
       

For a <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE</b> request, this member holds a flag that indicates the profile
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

For the <b>BRB_L2CA_OPEN_ENHANCED_CHANNEL</b> BRB, this member contains the response from the remote device to
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



#### If during a call to the BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE BRB the 
       Response member is set to CONNECT_RSP_RESULT_PENDING, this member is valid and contains one of
       the following values:



#### CONNECT_RSP_STATUS_AUTHENTICATION_PENDING



#### CONNECT_RSP_STATUS_AUTHORIZATION_PENDING



#### CONNECT_RSP_STATUS_NO_INFORMATION



## -remarks


Profile drivers can use CM_BASIC | CM_RETRANSMISSION_AND_FLOW, or CM_BASIC | CM_STREAMING modes for the <b>Flags</b> member. This indicates to open an enhanced retransmission mode, or streaming mode channel if possible, and if not fall back to basic mode channel. 
A value of CM_RETRANSMISSION_AND_FLOW | CM_STREAMING is not supported.


