---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_CAPS
title: _NDIS_WWAN_DEVICE_CAPS (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_CAPS structure represents the capabilities of the MB device.
old-location: netvista\ndis_wwan_device_caps.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_DEVICE_CAPS structure"]
ms.keywords: "*PNDIS_WWAN_DEVICE_CAPS, NDIS_WWAN_DEVICE_CAPS, NDIS_WWAN_DEVICE_CAPS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_CAPS, PNDIS_WWAN_DEVICE_CAPS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_fb40a6ef-20ae-4623-91e6-b69196e6e518.xml, _NDIS_WWAN_DEVICE_CAPS, ndiswwan/NDIS_WWAN_DEVICE_CAPS, ndiswwan/PNDIS_WWAN_DEVICE_CAPS, netvista.ndis_wwan_device_caps"
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
req.typenames: NDIS_WWAN_DEVICE_CAPS, *PNDIS_WWAN_DEVICE_CAPS
f1_keywords:
 - _NDIS_WWAN_DEVICE_CAPS
 - ndiswwan/_NDIS_WWAN_DEVICE_CAPS
 - PNDIS_WWAN_DEVICE_CAPS
 - ndiswwan/PNDIS_WWAN_DEVICE_CAPS
 - NDIS_WWAN_DEVICE_CAPS
 - ndiswwan/NDIS_WWAN_DEVICE_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_DEVICE_CAPS
---

# _NDIS_WWAN_DEVICE_CAPS structure


## -description

The NDIS_WWAN_DEVICE_CAPS structure represents the capabilities of the MB device.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_CAPS structure.
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
Windows 8 miniport drivers that follow the NDIS 6.30 specification should set this to NDIS_WWAN_DEVICE_CAPS_REVISION_2. Windows 7 miniport drivers that follow the NDIS 6.20 specification should set this to NDIS_WWAN_DEVICE_CAPS_REVISION_1.

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_CAPS)

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  You must specify NDIS_WWAN_DEVICE_CAPS_REVISION_2 in <b>Revision</b> to use the Windows 8 members of <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>.</div>
<div> </div>
For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field uStatus

The status of the device capabilities query. The following table shows the possible values for
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
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed to retrieve the capabilities for the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        when the ready-state is not 
        <b>WwanReadyStateOff</b>.

</td>
</tr>
</table>

### -field DeviceCaps

A formatted 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a> object that represents
     the capabilities of the MB device.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>
