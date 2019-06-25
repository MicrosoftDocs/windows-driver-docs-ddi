---
UID: NS:ndiswwan._NDIS_WWAN_SERVICE_ACTIVATION
title: _NDIS_WWAN_SERVICE_ACTIVATION (ndiswwan.h)
description: The NDIS_WWAN_SERVICE_ACTIVATION structure represents the command that is used to set the service activation state of the MB device in order to obtain access to the provider's network.
old-location: netvista\ndis_wwan_service_activation.htm
tech.root: netvista
ms.assetid: 0dbfa56f-a755-402d-b403-a04fc183c031
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SERVICE_ACTIVATION, NDIS_WWAN_SERVICE_ACTIVATION, NDIS_WWAN_SERVICE_ACTIVATION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SERVICE_ACTIVATION, PNDIS_WWAN_SERVICE_ACTIVATION structure pointer [Network Drivers Starting with Windows Vista], WwanRef_78a89315-d2f0-460f-9c8b-b6bf92d3b267.xml, _NDIS_WWAN_SERVICE_ACTIVATION, ndiswwan/NDIS_WWAN_SERVICE_ACTIVATION, ndiswwan/PNDIS_WWAN_SERVICE_ACTIVATION, netvista.ndis_wwan_service_activation"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndiswwan.h
api_name:
- NDIS_WWAN_SERVICE_ACTIVATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SERVICE_ACTIVATION, *PNDIS_WWAN_SERVICE_ACTIVATION
---

# _NDIS_WWAN_SERVICE_ACTIVATION structure


## -description


The NDIS_WWAN_SERVICE_ACTIVATION structure represents the command that is used to set the service
  activation state of the MB device in order to obtain access to the provider's network.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SERVICE_ACTIVATION
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
NDIS_WWAN_SERVICE_ACTIVATION _REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SERVICE_ACTIVATION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field ServiceActivation

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_service_activation">WWAN_SERVICE_ACTIVATION</a> structure
     that represents the service activation state of the device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_service_activation">WWAN_SERVICE_ACTIVATION</a>
 

 

