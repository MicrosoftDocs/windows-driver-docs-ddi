---
UID: NS:ndiswwan._NDIS_WWAN_HOME_PROVIDER2
title: _NDIS_WWAN_HOME_PROVIDER2 (ndiswwan.h)
description: The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider.
old-location: netvista\ndis_wwan_home_provider2.htm
tech.root: netvista
ms.assetid: B01039CF-F4AC-4374-BBB8-ACB204BC40E2
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_HOME_PROVIDER2, NDIS_WWAN_HOME_PROVIDER2, NDIS_WWAN_HOME_PROVIDER2 structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_HOME_PROVIDER2, PNDIS_WWAN_HOME_PROVIDER2 structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_HOME_PROVIDER2, ndiswwan/NDIS_WWAN_HOME_PROVIDER2, ndiswwan/PNDIS_WWAN_HOME_PROVIDER2, netvista.ndis_wwan_home_provider2"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_HOME_PROVIDER2"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
- NDIS_WWAN_HOME_PROVIDER2
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_HOME_PROVIDER2, *PNDIS_WWAN_HOME_PROVIDER2
---

# _NDIS_WWAN_HOME_PROVIDER2 structure


## -description


The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_HOME_PROVIDER2 structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
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
NDIS_WWAN_HOME_PROVIDER_REVISION_2

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_HOME_PROVIDER2)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the home provider operation.


### -field Provider

A formatted <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_provider2">WWAN_PROVIDER2</a> object that describes the details of a home network provider.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_provider2">WWAN_PROVIDER2</a>
 

 

