---
UID: NS:wwan._WWAN_PROVIDER
title: "_WWAN_PROVIDER"
author: windows-driver-content
description: The WWAN_PROVIDER structure represents details about a network provider.
old-location: netvista\wwan_provider.htm
old-project: netvista
ms.assetid: 2bca3123-3ac4-44fe-8d47-051314ef3cb7
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_PROVIDER, PWWAN_PROVIDER, PWWAN_PROVIDER structure pointer [Network Drivers Starting with Windows Vista], WWAN_PROVIDER, WWAN_PROVIDER structure [Network Drivers Starting with Windows Vista], WwanRef_a76aa69a-8c66-40a4-bda0-5ce66cc57790.xml, _WWAN_PROVIDER, netvista.wwan_provider, wwan/PWWAN_PROVIDER, wwan/WWAN_PROVIDER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	WWAN_PROVIDER
product:
- Windows
targetos: Windows
req.typenames: WWAN_PROVIDER, *PWWAN_PROVIDER
---

# _WWAN_PROVIDER structure


## -description


The WWAN_PROVIDER structure represents details about a network provider.


## -struct-fields




### -field ProviderId

A NULL-terminated numeric (0-9) string that represents the network provider identity.
     

For GSM-based networks, this string is a concatenation of a three-digit Mobile Country Code (MCC) and
     a two or three-digit Mobile Network Code (MNC). GSM-based carriers may have more than one MNC, and hence
     more than one 
     <b>ProviderId</b> .

For CDMA-based networks, this string is a five-digit System ID (SID). Generally a CDMA-based carrier
     has more than one SID. Typically, the carrier has one SID for each market, which is usually divided
     geographically within a nation by regulations, such as Metropolitan Statistical Areas (MSA) in the
     United States of America. Miniport drivers of CDMA-based devices must specify
     WWAN_CDMA_DEFAULT_PROVIDER_ID if this information is not available.


### -field ProviderState

A value that represents the various states that the network provider's entry can be tagged with.
     The following table shows the possible values that miniport drivers should specify (one or more values
     can be specified).
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_HOME

</td>
<td>
The network provider is the home operator.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_FORBIDDEN

</td>
<td>
The network provider is on the forbidden list.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_PREFERRED

</td>
<td>
The network provider is on the preferred list.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_VISIBLE

</td>
<td>
The network provider is visible.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_REGISTERED

</td>
<td>
The network provider is currently registered by the device.

</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_UNKNOWN

</td>
<td>
The network provider state is unknown.

</td>
</tr>
</table>
 

Some values in the previous table apply only to specific object identifiers (OIDs). The following
     table shows the associations between those values and related OIDs.

<table>
<tr>
<th>Value</th>
<th>OID</th>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_HOME

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569826">OID_WWAN_HOME_PROVIDER</a>


</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_FORBIDDEN

WWAN_PROVIDER_STATE_PREFERRED

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>


</td>
</tr>
<tr>
<td>
WWAN_PROVIDER_STATE_VISIBLE

WWAN_PROVIDER_STATE_REGISTERED

WWAN_PROVIDER_STATE_HOME

WWAN_PROVIDER_STATE_PREFERRED

WWAN_PROVIDER_STATE_FORBIDDEN

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a>


</td>
</tr>
</table>
 


### -field ProviderName

A NULL-terminated string that represents the network provider's name. This member is limited to,
     at most, WWAN_PROVIDERNAME_LEN characters.
     

For GSM-based networks, if the Preferred Presentation of Country Initials and Mobile Network Name
     (PPCI&amp;N) is longer than WWAN_PROVIDERNAME_LEN characters, the miniport driver should abbreviate the
     network name.

This member is ignored when the MB Service sets the preferred provider list.

Miniport drivers should specify a <b>NULL</b> string for devices that do not have this
     information.


### -field WwanDataClass

A bitmap that represents the data-class(es) that the device supports. For a detailed list of
     values, see the 
     <b>WwanDataClass</b> member of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a>.
     

This member can be ignored when queried for OID_WWAN_HOME_PROVIDER.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567909">NDIS_WWAN_HOME_PROVIDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567913">NDIS_WWAN_PREFERRED_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567948">NDIS_WWAN_VISIBLE_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a>
 

 

