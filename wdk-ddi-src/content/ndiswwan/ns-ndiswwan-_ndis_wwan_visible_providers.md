---
UID: NS:ndiswwan._NDIS_WWAN_VISIBLE_PROVIDERS
title: "_NDIS_WWAN_VISIBLE_PROVIDERS"
author: windows-driver-content
description: The NDIS_WWAN_VISIBLE_PROVIDERS structure represents a list of visible providers and the number of providers in the list.
old-location: netvista\ndis_wwan_visible_providers.htm
old-project: netvista
ms.assetid: ed30def8-41c5-4fa9-8098-80f47ddaaa99
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WwanRef_45997454-b06e-4291-82f5-57e29d8afa7e.xml, *PNDIS_WWAN_VISIBLE_PROVIDERS, _NDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], netvista.ndis_wwan_visible_providers, NDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS structure [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_VISIBLE_PROVIDERS, ndiswwan/PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_VISIBLE_PROVIDERS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# _NDIS_WWAN_VISIBLE_PROVIDERS structure


## -description


The NDIS_WWAN_VISIBLE_PROVIDERS structure represents a list of visible providers and the number of
  providers in the list.


## -syntax


````
typedef struct _NDIS_WWAN_VISIBLE_PROVIDERS {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_LIST_HEADER   VisibleListHeader;
} NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS;
````


## -struct-fields




#### - Header

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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


#### - uStatus

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


#### - VisibleListHeader

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a> object that represents a
     list of visible providers and the number of providers in the list.
     

This member points to the list of <a href="..\wwan\ns-wwan-_wwan_provider2.md">WWAN_PROVIDER2</a> structures that use the WWAN_LIST_HEADER structure. <b>WwanDataClass</b> flags describe the presence of the specific data access technology and can be set to any combination according to the availability of the data-classes


## -see-also

<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_VISIBLE_PROVIDERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

