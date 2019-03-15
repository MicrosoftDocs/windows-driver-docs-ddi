---
UID: NS:ndiswwan._NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS
title: _NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS (ndiswwan.h)
description: The NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multi-carrier providers and the number of providers in the list.
old-location: netvista\ndis_wwan_preferred_multicarrier_providers.htm
tech.root: netvista
ms.assetid: 4856D1DF-8A31-4290-91C6-A4FC289BDC35
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, PNDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, ndiswwan/NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, ndiswwan/PNDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, netvista.ndis_wwan_preferred_multicarrier_providers"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
- ndiswwan.h
api_name:
- NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS, *PNDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS
---

# _NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure


## -description


The NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multi-carrier providers and the number of providers in the list.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PREFERRED_MULTICARRIER_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

Miniport drivers must set this member to WWAN_STATUS_SUCCESS for unsolicited events. WWAN_STATUS_SUCCESS is also specified for successful execution of OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS <i>set</i> requests.  The following table shows other possible error status codes (other members need not be updated by miniport driver):

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Meaning</b>

</td>
</tr>
<tr>
<td>
WWAN_STATUS_READ_FAILURE

</td>
<td>
Reading information from the device failed

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
A <i>set</i> request is not supported

</td>
</tr>
</table>
 

<table></table>
 


### -field PreferredListHeader

 A formatted WWAN_LIST_HEADER object that represents a list of preferred multi-carrier providers, including the number of providers in the list.

These point to the list of the WWAN_PROVIDER2 by using the WWAN_LIST_HEADER structure. <b>WwanDataClass</b> flags describe the preference of the specific data access technology and can be set to any combination within its own cellular class.
Response to  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a><i>set </i> requests must contain zero elements in the <b>PreferredListHeader</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>
 

 

