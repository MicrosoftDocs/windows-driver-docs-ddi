---
UID: NS:ndiswwan._NDIS_WWAN_VISIBLE_PROVIDERS
title: "_NDIS_WWAN_VISIBLE_PROVIDERS" (ndiswwan.h)
description: The NDIS_WWAN_VISIBLE_PROVIDERS structure represents a list of visible providers and the number of providers in the list.
old-location: netvista\ndis_wwan_visible_providers.htm
tech.root: netvista
ms.assetid: ed30def8-41c5-4fa9-8098-80f47ddaaa99
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_45997454-b06e-4291-82f5-57e29d8afa7e.xml, _NDIS_WWAN_VISIBLE_PROVIDERS, ndiswwan/NDIS_WWAN_VISIBLE_PROVIDERS, ndiswwan/PNDIS_WWAN_VISIBLE_PROVIDERS, netvista.ndis_wwan_visible_providers"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
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
-	ndiswwan.h
api_name:
-	NDIS_WWAN_VISIBLE_PROVIDERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# _NDIS_WWAN_VISIBLE_PROVIDERS structure


## -description


The NDIS_WWAN_VISIBLE_PROVIDERS structure represents a list of visible providers and the number of
  providers in the list.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_VISIBLE_PROVIDERS
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
NDIS_WWAN_VISIBLE_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_VISIBLE_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

A miniport driver must set this to WWAN_STATUS_SUCCESS for successful execution of query to the
     OID_WWAN_VISIBLE_PROVIDER.
     

The following table shows the other possible error status codes (other members need not be updated by
     miniport driver).

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
Device requires PIN value input.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Unable to get visible list.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
A SIM card is not inserted in the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PROVIDERS_NOT_FOUND

</td>
<td>
No providers are found. Device seems to be in no network coverage.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
The device is busy and unable to scan. This can happen if the device does a destructive scan (for
        example, a scan may result in current registered state or PDP activation to be changed to deregister
        or PDP deactivation).

</td>
</tr>
<tr>
<td>
WWAN_STATUS_RADIO_POWER_OFF

</td>
<td>
Unable to scan. Radio is switched off.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SERVICE_NOT_ACTIVATED

</td>
<td>
Service activation has failed. Subscription has expired. Device does not allow scanning.

</td>
</tr>
</table>
 


### -field VisibleListHeader

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a> object that represents a
     list of visible providers and the number of providers in the list.
     

This member points to the list of <a href="https://msdn.microsoft.com/library/windows/hardware/hh464135">WWAN_PROVIDER2</a> structures that use the WWAN_LIST_HEADER structure. <b>WwanDataClass</b> flags describe the presence of the specific data access technology and can be set to any combination according to the availability of the data-classes


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>
 

 

