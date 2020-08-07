---
UID: NS:ndiswwan._NDIS_WWAN_PIN_LIST
title: _NDIS_WWAN_PIN_LIST (ndiswwan.h)
description: The NDIS_WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs).
old-location: netvista\ndis_wwan_pin_list.htm
tech.root: netvista
ms.assetid: 1d3c1084-8f51-4c8a-813e-6700d60c3dab
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_PIN_LIST structure"]
ms.keywords: "*PNDIS_WWAN_PIN_LIST, NDIS_WWAN_PIN_LIST, NDIS_WWAN_PIN_LIST structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PIN_LIST, PNDIS_WWAN_PIN_LIST structure pointer [Network Drivers Starting with Windows Vista], WwanRef_783d82e8-71ad-488c-be54-4bd316b949d7.xml, _NDIS_WWAN_PIN_LIST, ndiswwan/NDIS_WWAN_PIN_LIST, ndiswwan/PNDIS_WWAN_PIN_LIST, netvista.ndis_wwan_pin_list"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_PIN_LIST"
 - "NDIS_WWAN_PIN_LIST"
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
- NDIS_WWAN_PIN_LIST
targetos: Windows
req.typenames: NDIS_WWAN_PIN_LIST, *PNDIS_WWAN_PIN_LIST
---

# _NDIS_WWAN_PIN_LIST structure


## -description


The NDIS_WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers
  (PINs).


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PIN_LIST structure. The
     MB Service sets the header with the values that are shown in the following table when it sends the data
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
NDIS_WWAN_PIN_LIST_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PIN_LIST)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the PIN list operation. The following table shows the possible values for this.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
The PIN list operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The PIN list operation failed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The PIN list operation failed because a PIN must be entered before this operation can proceed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The PIN list operation failed because the SIM card is not inserted.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
</table>
 


### -field PinList

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_list">WWAN_PIN_LIST</a> object that represents a list
     of descriptions of Personal Identification Numbers (PINs).


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_list">WWAN_PIN_LIST</a>
 

 

