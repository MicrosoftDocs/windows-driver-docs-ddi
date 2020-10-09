---
UID: NS:wwan._WWAN_CONTEXT_STATE
title: _WWAN_CONTEXT_STATE (wwan.h)
description: The WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB device.
old-location: netvista\wwan_context_state.htm
tech.root: netvista
ms.assetid: 0b2a2a94-6c1a-439f-8d54-cc43e79b3b15
ms.date: 05/02/2018
keywords: ["WWAN_CONTEXT_STATE structure"]
ms.keywords: "*PWWAN_CONTEXT_STATE, PWWAN_CONTEXT_STATE, PWWAN_CONTEXT_STATE structure pointer [Network Drivers Starting with Windows Vista], WWAN_CONTEXT_STATE, WWAN_CONTEXT_STATE structure [Network Drivers Starting with Windows Vista], WwanRef_ff03afab-0fc4-4469-8a2d-f5d2a770f08d.xml, _WWAN_CONTEXT_STATE, netvista.wwan_context_state, wwan/PWWAN_CONTEXT_STATE, wwan/WWAN_CONTEXT_STATE"
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
targetos: Windows
req.typenames: WWAN_CONTEXT_STATE, *PWWAN_CONTEXT_STATE
f1_keywords:
 - _WWAN_CONTEXT_STATE
 - wwan/_WWAN_CONTEXT_STATE
 - PWWAN_CONTEXT_STATE
 - wwan/PWWAN_CONTEXT_STATE
 - WWAN_CONTEXT_STATE
 - wwan/WWAN_CONTEXT_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_CONTEXT_STATE
---

# _WWAN_CONTEXT_STATE structure


## -description

The WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB
  device.

## -struct-fields

### -field uNwError

A network-specific error. The following table shows the connection failure values as documented in
     the 
     <i>3GPP TS 24.008 Specification</i>.
     

<table>
<tr>
<th>3GPP 24.008 cause code</th>
<th>Interpretation of cause code</th>
</tr>
<tr>
<td>
8 - Operator determined barring

</td>
<td>
Packet data service is blocked by the operator.

</td>
</tr>
<tr>
<td>
26 - Insufficient resources

</td>
<td>
Context cannot be activated because of insufficient resources on network.

</td>
</tr>
<tr>
<td>
27 - Missing or unknown Access Point Name (APN)

</td>
<td>
No APN or unknown APN is provided in the activation request.

</td>
</tr>
<tr>
<td>
29 , 30, 31 - User authentication failed

</td>
<td>
Wrong user name or password provided in the activation request.

</td>
</tr>
<tr>
<td>
32 - Service option not supported

</td>
<td>
GPRS is not supported by the network.

</td>
</tr>
<tr>
<td>
33 - Requested service option is not subscribed

</td>
<td>
Requested service (GPRS) is not subscribed by the user.

</td>
</tr>
<tr>
<td>
34 - Service option is temporarily out of order

</td>
<td>
Packet data service is temporarily out of order. User must retry later.

</td>
</tr>
<tr>
<td>
43 - Unknown Packet Data Protocol (PDP) context

</td>
<td>
No APN or unknown APN is provided in the activation request.

</td>
</tr>
</table>

### -field ConnectionId

The MB Service specifies a value for this member at the time of the connect request by using
     OID_WWAN_CONNECT. Miniport drivers must copy this value and use it when they notify the MB Service on
     subsequent connection state changes.

### -field ActivationState

The current activation state of the device.

### -field VoiceCallState

The current voice call state of the device.

### -field IPType

A value from the WWAN_IP_TYPE enumeration that specifies the type of IP.

### -field ConnectionMedia

## -remarks

<i>Set</i> OID requests as well as unsolicited status events use the 
    <b>uNwError</b> member. If there is no network specific error or the network specific error is not known,
    miniport drivers should set this member to 0.

The following points provide guidelines on returning network specific error in different
    scenarios:

<ul>
<li>
If a set request fails, miniport drivers should return the network specific error code. In this
      case, the miniport driver should set the 
      <b>uStatus</b> member of the NDIS_WWAN_CONTEXT_STATE structure to WWAN_STATUS_FAILURE, or a more
      specific error like WWAN_STAUS_INVALID_ACCESS_STRING or WWAN_STATUS_INVALID_USER_NAME_PWD, and set the 
      <b>uNwError</b> member to the network specific error code.

</li>
<li>
Whenever the device context activation state changes because of network initiated context deactivate
      then unsolicited status events should include the network specific error. In this case, the miniport
      driver should set the 
      <b>uStatus</b> member of the NDIS_WWAN_CONTEXT_STATE structure to WWAN_STATUS_SUCCESS, and set the 
      <b>uNwError</b> member to the network specific error code.

</li>
</ul>
Miniport drivers can provide additional error codes as defined by the GSM standards specification of
    context activation error codes returned by the network. For example, miniport drivers can communicate the
    3GPP specification TS 24.008 context activation error codes, such as error code 8 (Operator determined
    barring), to the MB Service through the 
    <b>uNwError</b> member. There is no standard available for CDMA-based network specific error codes.
    CDMA-based devices and networks can return network specific error code information using the 
    <b>uNwError</b> member.

In case of response to the NDIS_WWAN_SET_CONTEXT_STATE, use this member to provide additional error
    codes returned by the network.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_context_state">NDIS_WWAN_CONTEXT_STATE</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_activation_state">WWAN_ACTIVATION_STATE</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_voice_call_state">WWAN_VOICE_CALL_STATE</a>