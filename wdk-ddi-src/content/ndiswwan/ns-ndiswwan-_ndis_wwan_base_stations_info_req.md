---
UID: NS:ndiswwan._NDIS_WWAN_BASE_STATIONS_INFO_REQ
title: "_NDIS_WWAN_BASE_STATIONS_INFO_REQ"
author: windows-driver-content
description: The NDIS_WWAN_BASE_STATIONS_INFO_REQ structure is used in OID_WWAN_BASE_STATIONS_INFO query requests to configure aspects of cellular base station information to be used in response.
old-location: netvista\ndis_wwan_base_stations_info_req.htm
old-project: netvista
ms.assetid: 4327021B-93FB-4605-B7D1-A7A6D661C8DF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_NDIS_WWAN_BASE_STATIONS_INFO_REQ, ndiswwan/PNDIS_WWAN_BASE_STATIONS_INFO_REQ, PNDIS_WWAN_BASE_STATIONS_INFO_REQ structure pointer [Network Drivers Starting with Windows Vista], NDIS_WWAN_BASE_STATIONS_INFO_REQ, PNDIS_WWAN_BASE_STATIONS_INFO_REQ, *PNDIS_WWAN_BASE_STATIONS_INFO_REQ, NDIS_WWAN_BASE_STATIONS_INFO_REQ structure [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_BASE_STATIONS_INFO_REQ, netvista.ndis_wwan_base_stations_info_req"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_BASE_STATIONS_INFO_REQ
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_BASE_STATIONS_INFO_REQ, NDIS_WWAN_BASE_STATIONS_INFO_REQ"
---

# _NDIS_WWAN_BASE_STATIONS_INFO_REQ structure


## -description


The <b>NDIS_WWAN_BASE_STATIONS_INFO_REQ</b> structure is used in <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-base-stations-info">OID_WWAN_BASE_STATIONS_INFO</a> query requests to configure aspects of cellular base station information to be used in response.


## -syntax


````
typedef struct _NDIS_WWAN_BASE_STATIONS_INFO_REQ {
  NDIS_OBJECT_HEADER          Header;
  WWAN_BASE_STATIONS_INFO_REQ BaseStationsInfoRequest;
} NDIS_WWAN_BASE_STATIONS_INFO_REQ, *PNDIS_WWAN_BASE_STATIONS_INFO_REQ;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field BaseStationsInfoRequest

A formatted <a href="..\wwan\ns-wwan-_wwan_base_stations_info_req.md">WWAN_BASE_STATIONS_INFO_REQ</a> structure that specifies the aspects of base stations information that are requested.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-base-stations-info">OID_WWAN_BASE_STATIONS_INFO</a>

<a href="..\wwan\ns-wwan-_wwan_base_stations_info_req.md">WWAN_BASE_STATIONS_INFO_REQ</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_BASE_STATIONS_INFO_REQ structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

