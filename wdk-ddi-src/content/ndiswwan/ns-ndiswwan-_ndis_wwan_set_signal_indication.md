---
UID: NS:ndiswwan._NDIS_WWAN_SET_SIGNAL_INDICATION
title: _NDIS_WWAN_SET_SIGNAL_INDICATION (ndiswwan.h)
description: The NDIS_WWAN_SET_SIGNAL_INDICATION structure represents the signal indication of the MB device.
old-location: netvista\ndis_wwan_set_signal_indication.htm
tech.root: netvista
ms.assetid: 6ef6fdd4-7d52-436a-96ee-ed83fab33e7b
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_SIGNAL_INDICATION, NDIS_WWAN_SET_SIGNAL_INDICATION, NDIS_WWAN_SET_SIGNAL_INDICATION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_SIGNAL_INDICATION, PNDIS_WWAN_SET_SIGNAL_INDICATION structure pointer [Network Drivers Starting with Windows Vista], WwanRef_da95b173-97da-4e41-9628-2a101a851f1c.xml, _NDIS_WWAN_SET_SIGNAL_INDICATION, ndiswwan/NDIS_WWAN_SET_SIGNAL_INDICATION, ndiswwan/PNDIS_WWAN_SET_SIGNAL_INDICATION, netvista.ndis_wwan_set_signal_indication"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SET_SIGNAL_INDICATION"
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
- NDIS_WWAN_SET_SIGNAL_INDICATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_SIGNAL_INDICATION, *PNDIS_WWAN_SET_SIGNAL_INDICATION
---

# _NDIS_WWAN_SET_SIGNAL_INDICATION structure


## -description


The NDIS_WWAN_SET_SIGNAL_INDICATION structure represents the signal indication of the MB
  device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_SIGNAL_INDICATION
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
NDIS_WWAN_SET_SIGNAL_INDICATION_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_SIGNAL_INDICATION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field SignalIndication

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_signal_indication">
     WWAN_SET_SIGNAL_INDICATION</a> object that represents the frequency of RSSI interval and RSSI
     threshold notifications.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_signal_indication">WWAN_SET_SIGNAL_INDICATION</a>
 

 

