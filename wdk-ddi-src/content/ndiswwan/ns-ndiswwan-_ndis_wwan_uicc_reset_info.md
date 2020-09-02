---
UID: NS:ndiswwan._NDIS_WWAN_UICC_RESET_INFO
title: _NDIS_WWAN_UICC_RESET_INFO (ndiswwan.h)
description: The NDIS_WWAN_UICC_RESET_INFO structure represents the passthrough status of a modem miniport adapter for a UICC smart card.
old-location: netvista\ndis_wwan_uicc_reset_info.htm
tech.root: netvista
ms.assetid: 9CBAFC44-187A-41ED-9405-1208167AC75D
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_UICC_RESET_INFO structure"]
ms.keywords: "*PNDIS_WWAN_UICC_RESET_INFO, NDIS_WWAN_UICC_RESET_INFO, NDIS_WWAN_UICC_RESET_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_UICC_RESET_INFO, PNDIS_WWAN_UICC_RESET_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_UICC_RESET_INFO, ndiswwan/NDIS_WWAN_UICC_RESET_INFO, ndiswwan/PNDIS_WWAN_UICC_RESET_INFO, netvista.ndis_wwan_uicc_reset_info"
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
targetos: Windows
req.typenames: NDIS_WWAN_UICC_RESET_INFO, *PNDIS_WWAN_UICC_RESET_INFO
f1_keywords:
 - _NDIS_WWAN_UICC_RESET_INFO
 - ndiswwan/_NDIS_WWAN_UICC_RESET_INFO
 - PNDIS_WWAN_UICC_RESET_INFO
 - ndiswwan/PNDIS_WWAN_UICC_RESET_INFO
 - NDIS_WWAN_UICC_RESET_INFO
 - ndiswwan/NDIS_WWAN_UICC_RESET_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_UICC_RESET_INFO
---

# _NDIS_WWAN_UICC_RESET_INFO structure


## -description

The <b>NDIS_WWAN_UICC_RESET_INFO</b> structure represents the passthrough status of a modem miniport adapter for a UICC smart card.

## -struct-fields

### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_UICC_RESET_INFO</b> structure.
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
NDIS_WWAN_UICC_RESET_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_UICC_RESET_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field uStatus

The status of system capability. The following table shows the possible values for
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
The operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support this OID.

</td>
</tr>
</table>

### -field UiccResetInfo

A formatted <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_uicc_reset_info">WWAN_UICC_RESET_INFO</a> structure that represents the passthrough status of the miniport adapter.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-reset">OID_WWAN_UICC_RESET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_uicc_reset_info">WWAN_UICC_RESET_INFO</a>

