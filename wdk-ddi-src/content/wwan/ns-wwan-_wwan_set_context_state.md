---
UID: NS:wwan._WWAN_SET_CONTEXT_STATE
title: "_WWAN_SET_CONTEXT_STATE"
author: windows-driver-content
description: The WWAN_SET_CONTEXT_STATE structure represents the command to set the Packet Data Protocol (PDP) context state of the MB device.
old-location: netvista\wwan_set_context_state.htm
old-project: netvista
ms.assetid: f1ed31af-97a7-472e-b834-577470950335
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_SET_CONTEXT_STATE, PWWAN_SET_CONTEXT_STATE, PWWAN_SET_CONTEXT_STATE structure pointer [Network Drivers Starting with Windows Vista], WWAN_SET_CONTEXT_STATE, WWAN_SET_CONTEXT_STATE structure [Network Drivers Starting with Windows Vista], WwanRef_a4c14223-1c16-4f87-8820-2a45f04bb62d.xml, _WWAN_SET_CONTEXT_STATE, netvista.wwan_set_context_state, wwan/PWWAN_SET_CONTEXT_STATE, wwan/WWAN_SET_CONTEXT_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_SET_CONTEXT_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_SET_CONTEXT_STATE, *PWWAN_SET_CONTEXT_STATE
req.product: Windows 10 or later.
---

# _WWAN_SET_CONTEXT_STATE structure


## -description


The WWAN_SET_CONTEXT_STATE structure represents the command to set the Packet Data Protocol (PDP)
  context state of the MB device.


## -struct-fields




### -field ConnectionId

MB Service specifies this member to uniquely identify the PDP Context and its corresponding state.
     

The MB Service uses the value in this member to uniquely identify the current active context across
     MB network adapters.

The miniport driver must use the value in this member when completing 
     <i>set</i> requests. The MB Service uses the value in this member in subsequent 
     <i>query</i> requests as well as disconnect requests to the miniport driver.


### -field ActivationCommand

Activate or deactivate a PDP context that is referenced in the 
     <b>ConnectionId</b> member. The following table shows the possible values a miniport driver can specify.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WwanActivationCommandActivate

</td>
<td>
Activate PDP context referred to by 
        <b>ConnectionId</b> .

</td>
</tr>
<tr>
<td>
WwanActivationCommandDeactivate

</td>
<td>
Deactivate a currently activated PDP context referred by 
        <b>ConnectionId</b> .

</td>
</tr>
</table>
 


### -field AccessString

A NULL-terminated string to access the network. For GSM-based networks, this would be an Access
     Point Name (APN) string such as "data.thephone-company.com". For CDMA-based networks, this might be a
     special dial code such as "#777" or a Network Access Identifier (NAI) such as
     "foo@thephone-company.com". This member can be <b>NULL</b>.
     

The size of the string should not exceed 100 bytes.


### -field UserName

A NULL-terminated string that represents the username to authenticate. This member can be
     <b>NULL</b>.


### -field Password

A NULL-terminated string that represents the username's password. This member can be <b>NULL</b>.


### -field Compression

A value from the WWAN_COMPRESSION enumeration that specifies whether compression should be used in
     the data connection for header and data. This member applies only to GSM-based devices. The MB Service
     sets this member to 
     <b>WwanCompressionNone</b> for CDMA-based devices.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WwanCompressionNone

</td>
<td>
No compression is applied.

</td>
</tr>
<tr>
<td>
WwanCompressionEnable

</td>
<td>
Enable header and data compression.

</td>
</tr>
</table>
 


### -field AuthType

A value from the WWAN_AUTH_PROTOCOL enumeration that specifies the authentication type to use for
     the PDP activation. This member applies only to GSM-based devices. The MB Service sets this member to 
     <b>WwanAuthProtocolNone</b> for CDMA-based devices.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WwanAuthProtocolNone

</td>
<td>
No authentication protocol.

</td>
</tr>
<tr>
<td>
WwanAuthProtocolPap

</td>
<td>
Unencrypted password authentication.

</td>
</tr>
<tr>
<td>
WwanAuthProtocolChap

</td>
<td>
Use the Challenge Handshake Authentication Protocol (CHAP).

</td>
</tr>
<tr>
<td>
WwanAuthProtocolMsChapV2

</td>
<td>
Use the Microsoft Challenge Handshake Authentication Protocol (CHAP) v2.0.

</td>
</tr>
</table>
 


### -field IPType

A value from the WWAN_IP_TYPE enumeration that specifies the type of IP.


### -field MediaPreference

 


### -field ConnectionMediaSource

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567920">NDIS_WWAN_SET_CONTEXT_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571196">WWAN_ACTIVATION_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571198">WWAN_AUTH_PROTOCOL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571200">WWAN_COMPRESSION</a>
 

 

