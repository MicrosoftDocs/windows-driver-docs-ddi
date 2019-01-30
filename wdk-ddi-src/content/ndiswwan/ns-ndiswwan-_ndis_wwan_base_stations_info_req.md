---
UID: NS:ndiswwan._NDIS_WWAN_BASE_STATIONS_INFO_REQ
title: "_NDIS_WWAN_BASE_STATIONS_INFO_REQ" (ndiswwan.h)
description: The NDIS_WWAN_BASE_STATIONS_INFO_REQ structure is used in OID_WWAN_BASE_STATIONS_INFO query requests to configure aspects of cellular base station information to be used in response.
old-location: netvista\ndis_wwan_base_stations_info_req.htm
tech.root: netvista
ms.assetid: 4327021B-93FB-4605-B7D1-A7A6D661C8DF
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_BASE_STATIONS_INFO_REQ, NDIS_WWAN_BASE_STATIONS_INFO_REQ, NDIS_WWAN_BASE_STATIONS_INFO_REQ structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_BASE_STATIONS_INFO_REQ, PNDIS_WWAN_BASE_STATIONS_INFO_REQ structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_BASE_STATIONS_INFO_REQ, ndiswwan/NDIS_WWAN_BASE_STATIONS_INFO_REQ, ndiswwan/PNDIS_WWAN_BASE_STATIONS_INFO_REQ, netvista.ndis_wwan_base_stations_info_req"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	NDIS_WWAN_BASE_STATIONS_INFO_REQ
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_BASE_STATIONS_INFO_REQ, *PNDIS_WWAN_BASE_STATIONS_INFO_REQ
---

# _NDIS_WWAN_BASE_STATIONS_INFO_REQ structure


## -description


The <b>NDIS_WWAN_BASE_STATIONS_INFO_REQ</b> structure is used in <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-base-stations-info">OID_WWAN_BASE_STATIONS_INFO</a> query requests to configure aspects of cellular base station information to be used in response.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_BASE_STATIONS_INFO_REQ</b> structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
NDIS_WWAN_BASE_STATIONS_INFO_REQ_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_BASE_STATIONS_INFO_REQ)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field BaseStationsInfoRequest

A formatted <a href="https://msdn.microsoft.com/1948F98B-1F0B-4EB3-A2FF-01DA159B5EEB">WWAN_BASE_STATIONS_INFO_REQ</a> structure that specifies the aspects of base stations information that are requested.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-base-stations-info">OID_WWAN_BASE_STATIONS_INFO</a>



<a href="https://msdn.microsoft.com/1948F98B-1F0B-4EB3-A2FF-01DA159B5EEB">WWAN_BASE_STATIONS_INFO_REQ</a>
 

 

