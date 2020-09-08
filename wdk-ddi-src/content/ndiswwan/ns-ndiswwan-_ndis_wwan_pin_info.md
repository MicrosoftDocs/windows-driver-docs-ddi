---
UID: NS:ndiswwan._NDIS_WWAN_PIN_INFO
title: _NDIS_WWAN_PIN_INFO (ndiswwan.h)
description: The NDIS_WWAN_PIN_INFO structure represents the type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device.
old-location: netvista\ndis_wwan_pin_info.htm
tech.root: netvista
ms.assetid: 432e1d25-b7f4-4897-99dc-27ea14c851e2
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_PIN_INFO structure"]
ms.keywords: "*PNDIS_WWAN_PIN_INFO, NDIS_WWAN_PIN_INFO, NDIS_WWAN_PIN_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PIN_INFO, PNDIS_WWAN_PIN_INFO structure pointer [Network Drivers Starting with Windows Vista], WwanRef_9095fdd7-5593-439c-897a-1def216d3374.xml, _NDIS_WWAN_PIN_INFO, ndiswwan/NDIS_WWAN_PIN_INFO, ndiswwan/PNDIS_WWAN_PIN_INFO, netvista.ndis_wwan_pin_info"
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
targetos: Windows
req.typenames: NDIS_WWAN_PIN_INFO, *PNDIS_WWAN_PIN_INFO
f1_keywords:
 - _NDIS_WWAN_PIN_INFO
 - ndiswwan/_NDIS_WWAN_PIN_INFO
 - PNDIS_WWAN_PIN_INFO
 - ndiswwan/PNDIS_WWAN_PIN_INFO
 - NDIS_WWAN_PIN_INFO
 - ndiswwan/NDIS_WWAN_PIN_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_PIN_INFO
---

# _NDIS_WWAN_PIN_INFO structure


## -description

The NDIS_WWAN_PIN_INFO structure represents the type and PIN-entry state of Personal Identification
  Number (PIN) information required by the MB device.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_PIN_INFO structure. The
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
NDIS_WWAN_PIN_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PIN_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field uStatus

The status of the PIN info operation. The following table shows the possible values for this
     member.
     

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
Pin info operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
Pin info operation failed because the SIM card is not inserted.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Pin info operation failed.

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
<tr>
<td>
WWAN_STATUS_PIN_DISABLED

</td>
<td>
The operation failed because the PIN is disabled.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The operation failed because a PIN must be entered to proceed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because a 
        <i>set</i> on a corresponding PIN type is not supported by the device.

</td>
</tr>
</table>

### -field PinInfo

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_info">WWAN_PIN_INFO</a> object that represents the type
     and PIN-entry state of Personal Identification Number (PIN) information required by the device.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_info">WWAN_PIN_INFO</a>

