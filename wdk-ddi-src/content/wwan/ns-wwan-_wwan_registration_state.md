---
UID: NS:wwan._WWAN_REGISTRATION_STATE
title: "_WWAN_REGISTRATION_STATE"
author: windows-driver-content
description: The WWAN_REGISTRATION_STATE structure represents the registration state of the MB device.
old-location: netvista\wwan_registration_state.htm
old-project: netvista
ms.assetid: 72a41403-9e22-4212-955a-16e243f7af1d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WwanRef_ff7f3a8a-853b-43e3-95fb-ed4320806ad2.xml, PWWAN_REGISTRATION_STATE structure pointer [Network Drivers Starting with Windows Vista], PWWAN_REGISTRATION_STATE, wwan/PWWAN_REGISTRATION_STATE, WWAN_REGISTRATION_STATE, wwan/WWAN_REGISTRATION_STATE, netvista.wwan_registration_state, *PWWAN_REGISTRATION_STATE, WWAN_REGISTRATION_STATE structure [Network Drivers Starting with Windows Vista], _WWAN_REGISTRATION_STATE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_REGISTRATION_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_REGISTRATION_STATE, *PWWAN_REGISTRATION_STATE
req.product: Windows 10 or later.
---

# _WWAN_REGISTRATION_STATE structure


## -description


The WWAN_REGISTRATION_STATE structure represents the registration state of the MB device.


## -syntax


````
typedef struct _WWAN_REGISTRATION_STATE {
  ULONG               uNwError;
  WWAN_REGISTER_STATE RegisterState;
  WWAN_REGISTER_MODE  RegisterMode;
  WCHAR               ProviderId[WWAN_PROVIDERID_LEN];
  WCHAR               ProviderName[WWAN_PROVIDERNAME_LEN];
  WCHAR               RoamingText[WWAN_ROAMTEXT_LEN];
  DWORD               WwanRegFlags;
  WWAN_CELLULAR_CLASS CurrentCellularClass;
} WWAN_REGISTRATION_STATE, *PWWAN_REGISTRATION_STATE;
````


## -struct-fields




### -field uNwError

A network specific error, in the event of a registration failure. For more information about this
     member, see the following 
     "Remarks" section.


### -field RegisterState

The registration state of the device. For a list of defined values, see 
     <a href="..\wwan\ne-wwan-_wwan_register_state.md">WWAN_REGISTER_STATE</a>.
     

The 
     <b>WwanRegisterStatePartner</b> value indicates the device is roaming on a preferred partner network
     provider, whereas 
     <b>WwanRegisterStateRoaming</b> value indicates the device is just roaming. If the partner
     characterization of the roaming state is not available, the miniport driver should report 
     <b>WwanRegisterStateRoaming</b>.


### -field RegisterMode

The registration mode of the device. For a list of defined values, see 
     <a href="..\wwan\ne-wwan-_wwan_register_mode.md">WWAN_REGISTER_MODE</a>.


### -field ProviderId

A NULL-terminated numeric (0-9) string that represents the network provider identity.
     

For GSM-based networks, this string is a concatenation of a three-digit Mobile Country Code (MCC) and
     a two or three-digit Mobile Network Code (MNC). GSM-based carriers may have more than one MNC, and hence
     more than one 
     <b>ProviderId</b> .

For CDMA-based networks, this string is a five-digit System ID (SID). Generally, a CDMA-based carrier
     has more than one SID. Typically, a carrier has one SID for each market, which is usually divided
     geographically within a nation by regulations, such as Metropolitan Statistical Areas (MSA) in the
     United States of America. Miniport drivers of CDMA-based devices must specify
     WWAN_CDMA_DEFAULT_PROVIDER_ID if this information is not available.

When processing a 
     <i>query</i> request, and the registration state is in automatic register mode, this member contains the
     provider ID that the device is currently associated with (if applicable). When the registration state is
     in manual register mode, this member contains the provider ID that the device is requested to register
     with (even if the provider is unavailable).

When processing a 
     <i>set</i> request and the registration state is in manual mode, this contains the provider ID selected
     by the MB Service for the device to register with. When the registration state is in automatic register
     mode, this parameter is ignored.

CDMA 1xRTT providers must be set to WWAN_CDMA_DEFAULT_PROVIDER_ID if the provider ID is not
     available.


### -field ProviderName

A NULL-terminated string that represents the network provider's name. This member is limited to,
     at most, WWAN_PROVIDERNAME_LEN characters.
     

For GSM-based networks, if the Preferred Presentation of Country Initials and Mobile Network Name
     (PPCI&amp;N) is longer than twenty characters, the miniport driver should abbreviate the network
     name.

This member is ignored when the MB Service sets the preferred provider list.

Miniport drivers should specify a <b>NULL</b> string for devices that do not have this
     information.


### -field RoamingText

A NULL-terminated string to inform the user that the device is roaming. This member is limited to
     at most WWAN_ROAMTEXT_LEN characters.
     

This text should provide additional information to the user when the registration state is either 
     <b>WwanRegisterStatePartner</b> or 
     <b>WwanRegisterStateRoaming</b>. This member is optional.


### -field WwanRegFlags

Registration flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_REG_FLAGS_NONE

</td>
<td>
No registration flags.

</td>
</tr>
<tr>
<td>
WWAN_REG_FLAGS_NO_MANUAL_REG

</td>
<td>
No manual attach.

</td>
</tr>
<tr>
<td>
WWAN_REG_FLAGS_PS_AUTO_ATTACH

</td>
<td>
Iindicates that the MB device manages its own packet context. The MB Service will not send a packet detach to the miniport driver, but may send a packet attach.

</td>
</tr>
</table>
 


### -field CurrentCellularClass

The current cellular class of the registered network. For networks that only support a single cellular class this member should be set to that cellular class. For multi-mode capable networks the miniport driver sends  NDIS_STATUS_WWAN_REGISTER_STATE notifications to the MB service when the network changes its cellular class.


## -remarks



<i>Query</i> and 
    <i>set</i> OID requests as well as unsolicited status events use the 
    <b>uNwError</b> member. If there is no network specific error or the network specific error is not known,
    miniport drivers should set this member to zero. The 
    "Status Indication Structure" section in 
    <a href="https://msdn.microsoft.com/5f04b7fd-3df3-4efa-bb26-c7f4cd3c9ebd">MB Operational Semantics</a> shows the
    registration cause code failure values that are defined in the 
    <i>3GPP TS 24.008 Specification</i>.

The following points provide guidelines on returning network specific error in different
    scenarios:

<ul>
<li>
If network registration fails because of network specific error, miniport drivers should return the
      network specific error in response to 
      <i>query</i> requests. In this case, miniport drivers should set the 
      <b>uStatus</b> member of the NDIS_WWAN_REGISTRATION_STATE structure to WWAN_STATUS_SUCCESS and set the 
      <b>uNwError</b> member to the network specific error code.

</li>
<li>
If a 
      <i>set</i> request fails, miniport drivers should return the network specific error code. In this case,
      miniport drivers should set the 
      <b>uStatus</b> member of the NDIS_WWAN_REGISTRATION_STATE structure to WWAN_STATUS_FAILURE and set the 
      <b>uNwError</b> member to the network specific error code.

</li>
<li>
Whenever the device registration state changes because the network de-registers the device (for
      example, the network de-registered the device because the device's subscription expired) then
      unsolicited status events should include the network specific error. In this case, the miniport driver
      should set the 
      <b>uStatus</b> member of the NDIS_WWAN_REGISTRATION_STATE structure to WWAN_STATUS_SUCCESS and set the 
      <b>uNwError</b> member to the network specific error code.

</li>
</ul>
To return a network specific error when processing OID_WWAN_REGISTER_STATE requests, miniport drivers
    should set the 
    <b>uStatus</b> member of the NDIS_WWAN_REGISTRATION_STATE structure to WWAN_STATUS_FAILURE and set the 
    <b>uNwError</b> member to the network specific error code.

Miniport drivers can provide additional error codes as defined by the GSM standards specification of
    packet-attach error codes returned by the network. For example, miniport drivers can communicate the 3GPP
    specification TS 24.008 packet-attach error codes, such as error code 12 (Location area not allowed), to
    the MB Service through the 
    <b>uNwError</b> member.

Miniport drivers must report the cause code at the earliest possible instance. For example, if the MB
    device encounters one of these codes when attempting to register the device on with a network provider,
    the miniport driver should report it at that time.

Miniport drivers connected to a multi-mode network should indicate the cellular class change through a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567857">NDIS_STATUS_WWAN_REGISTER_STATE</a> notification.




## -see-also

<a href="..\wwan\ne-wwan-_wwan_register_mode.md">WWAN_REGISTER_MODE</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_registration_state.md">NDIS_WWAN_REGISTRATION_STATE</a>



<a href="..\wwan\ne-wwan-_wwan_register_state.md">WWAN_REGISTER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_REGISTRATION_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

