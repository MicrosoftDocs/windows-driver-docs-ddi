---
UID: NS:ndiswwan._NDIS_WWAN_PREFERRED_PROVIDERS
title: "_NDIS_WWAN_PREFERRED_PROVIDERS"
author: windows-driver-content
description: The NDIS_WWAN_PREFERRED_PROVIDERS structure represents a list of preferred providers including the number of providers in the list.
old-location: netvista\ndis_wwan_preferred_providers.htm
old-project: netvista
ms.assetid: cbbbf7d2-cf24-47af-89e9-c27d577165e4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndiswwan/NDIS_WWAN_PREFERRED_PROVIDERS, NDIS_WWAN_PREFERRED_PROVIDERS, WwanRef_71564505-6147-416d-8178-0a7f5b30d07e.xml, _NDIS_WWAN_PREFERRED_PROVIDERS, *PNDIS_WWAN_PREFERRED_PROVIDERS, netvista.ndis_wwan_preferred_providers, PNDIS_WWAN_PREFERRED_PROVIDERS, PNDIS_WWAN_PREFERRED_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/PNDIS_WWAN_PREFERRED_PROVIDERS, NDIS_WWAN_PREFERRED_PROVIDERS structure [Network Drivers Starting with Windows Vista]
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
-	NDIS_WWAN_PREFERRED_PROVIDERS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_PREFERRED_PROVIDERS, *PNDIS_WWAN_PREFERRED_PROVIDERS
---

# _NDIS_WWAN_PREFERRED_PROVIDERS structure


## -description


The NDIS_WWAN_PREFERRED_PROVIDERS structure represents a list of preferred providers including the
  number of providers in the list.


## -syntax


````
typedef struct _NDIS_WWAN_PREFERRED_PROVIDERS {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_LIST_HEADER   PreferredListHeader;
} NDIS_WWAN_PREFERRED_PROVIDERS, *PNDIS_WWAN_PREFERRED_PROVIDERS;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PREFERRED_PROVIDERS
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
NDIS_WWAN_PREFERRED_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PREFERRED_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

Miniport driver must set this to WWAN_STATUS_SUCCESS for unsolicited events
     (NDIS_STATUS_INDICATION::RequestId = 0). WWAN_STATUS_SUCCESS is also set for successful execution of the
     NDIS_WWAN_SET_PREFERRED_PROVIDERS.
     

The following table shows other possible error status codes (other members need not be updated by
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
WWAN_STATUS_READ_FAILURE

</td>
<td>
Reading information from device or SIM card, or both, failed. For example, the SIM card does not
        have preferred providers information provisioned.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
Bad SIM detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
SIM not inserted in the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
A 
        <i>set</i> request is not supported.

</td>
</tr>
</table>
 


### -field PreferredListHeader

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a> object that represents a
     list of preferred providers, including the number of providers in the list.
     

These point to the list of <a href="..\wwan\ns-wwan-_wwan_provider2.md">WWAN_PROVIDER2</a> by using the WWAN_LIST_HEADER structure. 
     <b>WwanDataClass</b> flags describe the preference of the specific data access technology and can be set
     to any combination within its own cellular class.

Response to 
     <i>set</i> OID_WWAN_PREFERRED_PROVIDERS requests must contain zero elements in the 
     <b>PreferenceListHeader</b>.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PREFERRED_PROVIDERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

