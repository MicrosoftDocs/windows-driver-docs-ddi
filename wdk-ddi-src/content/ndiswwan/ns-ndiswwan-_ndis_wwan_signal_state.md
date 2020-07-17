---
UID: NS:ndiswwan._NDIS_WWAN_SIGNAL_STATE
title: _NDIS_WWAN_SIGNAL_STATE (ndiswwan.h)
description: The NDIS_WWAN_SIGNAL_STATE structure represents the signal state of the MB device.
old-location: netvista\ndis_wwan_signal_state.htm
tech.root: netvista
ms.assetid: 905f8566-ad98-454f-a5cd-8f4ff46c8118
ms.date: 04/05/2019
keywords: ["_NDIS_WWAN_SIGNAL_STATE structure"]
ms.keywords: "*PNDIS_WWAN_SIGNAL_STATE, NDIS_WWAN_SIGNAL_STATE, NDIS_WWAN_SIGNAL_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SIGNAL_STATE, PNDIS_WWAN_SIGNAL_STATE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_92027d1b-0311-4d61-b8cf-04518ee2863b.xml, _NDIS_WWAN_SIGNAL_STATE, ndiswwan/NDIS_WWAN_SIGNAL_STATE, ndiswwan/PNDIS_WWAN_SIGNAL_STATE, netvista.ndis_wwan_signal_state"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SIGNAL_STATE"
 - "NDIS_WWAN_SIGNAL_STATE"
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
- NDIS_WWAN_SIGNAL_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SIGNAL_STATE, *PNDIS_WWAN_SIGNAL_STATE
---

# _NDIS_WWAN_SIGNAL_STATE structure


## -description


The NDIS_WWAN_SIGNAL_STATE structure represents the signal state of the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SIGNAL_STATE structure.
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
Windows 10, version 1903 and later miniport drivers set this to NDIS_WWAN_SIGNAL_STATE_REVISION_3. Earlier miniport driver versions set this to NDIS_WWAN_SIGNAL_STATE_REVISION_1.

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SIGNAL_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the signal state operation.


### -field SignalState

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_signal_state">WWAN_SIGNAL_STATE</a> object that represents
     the signal state of the MB device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_signal_state">WWAN_SIGNAL_STATE</a>
 

 

