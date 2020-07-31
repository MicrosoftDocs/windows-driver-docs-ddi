---
UID: NS:ndiswwan._NDIS_WWAN_USSD_REQUEST
title: _NDIS_WWAN_USSD_REQUEST (ndiswwan.h)
description: The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS request.
old-location: netvista\ndis_wwan_ussd_request.htm
tech.root: netvista
ms.assetid: B98143A1-7F7D-4130-A388-72A21B89E6D8
ms.date: 05/02/2018
keywords: ["_NDIS_WWAN_USSD_REQUEST structure"]
ms.keywords: "*PNDIS_WWAN_USSD_REQUEST, NDIS_WWAN_USSD_REQUEST, NDIS_WWAN_USSD_REQUEST structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_USSD_REQUEST, PNDIS_WWAN_USSD_REQUEST structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_USSD_REQUEST, ndiswwan/NDIS_WWAN_USSD_REQUEST, ndiswwan/PNDIS_WWAN_USSD_REQUEST, netvista.ndis_wwan_ussd_request"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_USSD_REQUEST"
 - "NDIS_WWAN_USSD_REQUEST"
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
- NDIS_WWAN_USSD_REQUEST
targetos: Windows
req.typenames: NDIS_WWAN_USSD_REQUEST, *PNDIS_WWAN_USSD_REQUEST
---

# _NDIS_WWAN_USSD_REQUEST structure


## -description


The NDIS_WWAN_USSD_EVENT structure represents an Unstructured Supplementary Service Data (USSD) NDIS request.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_USSD_REQUEST structure. The MB Service sets the header with the values that are shown in the following table when it
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
NDIS_WWAN_USSD_REQUEST_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_USSD_REQUEST)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field UssdRequest

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ussd_request">WWAN_USSD_REQUEST</a> object that represents a USSD request.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ussd_request">WWAN_USSD_REQUEST</a>
 

 

