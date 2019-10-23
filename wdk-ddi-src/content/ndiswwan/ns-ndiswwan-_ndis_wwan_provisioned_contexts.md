---
UID: NS:ndiswwan._NDIS_WWAN_PROVISIONED_CONTEXTS
title: _NDIS_WWAN_PROVISIONED_CONTEXTS (ndiswwan.h)
description: The NDIS_WWAN_PROVISIONED_CONTEXTS structure represents a list of provisioned contexts and the number of provisioned contexts in the list.
old-location: netvista\ndis_wwan_provisioned_contexts.htm
tech.root: netvista
ms.assetid: ee4ba781-9adf-4eb0-8c3d-b11aac86c943
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_PROVISIONED_CONTEXTS, NDIS_WWAN_PROVISIONED_CONTEXTS, NDIS_WWAN_PROVISIONED_CONTEXTS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PROVISIONED_CONTEXTS, PNDIS_WWAN_PROVISIONED_CONTEXTS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_ad7bfe2b-eb11-45f9-a49d-a602df06b97f.xml, _NDIS_WWAN_PROVISIONED_CONTEXTS, ndiswwan/NDIS_WWAN_PROVISIONED_CONTEXTS, ndiswwan/PNDIS_WWAN_PROVISIONED_CONTEXTS, netvista.ndis_wwan_provisioned_contexts"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_PROVISIONED_CONTEXTS"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 7.
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
- NDIS_WWAN_PROVISIONED_CONTEXTS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_PROVISIONED_CONTEXTS, *PNDIS_WWAN_PROVISIONED_CONTEXTS
---

# _NDIS_WWAN_PROVISIONED_CONTEXTS structure


## -description


The NDIS_WWAN_PROVISIONED_CONTEXTS structure represents a list of provisioned contexts and the number
  of provisioned contexts in the list.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PROVISIONED_CONTEXTS
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
NDIS_WWAN_PROVISIONED_CONTEXTS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PROVISIONED_CONTEXTS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the provisioned context query or set operation. The following table shows the possible values for
     this member.
     

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
 The  operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed for a reason other than those listed here.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_PARAMETERS

</td>
<td>
The operation failed because of invalid parameters.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The operation failed because the device requires a PIN.

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
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The operation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support service activation.

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
WWAN_STATUS_READ_FAILURE

</td>
<td>
The operation failed because the device was unable to get provisioned contexts.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_WRITE_FAILURE

</td>
<td>
The operation failed because the update request was unsuccessful.

</td>
</tr>
</table>
 

The status of provisioned context set operation. The following table shows the possible value for
     this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_WRITE_FAILURE

</td>
<td>
The operation failed because the update request was unsuccessful.

</td>
</tr>
</table>
 


### -field ContextListHeader

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a> object that represents a
     list of provisioned contexts and the number of provisioned contexts in the list.


## -remarks



Miniport drivers should specify zero elements in the context list when they respond to
    OID_WWAN_PROVISIONED_CONTEXT 
    <i>set</i> requests.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a>
 

 

