---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_CAPS_EX
title: _NDIS_WWAN_DEVICE_CAPS_EX (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_CAPS_EX structure represents the capabilities of the MB device.
old-location: netvista\ndis_wwan_device_caps_ex.htm
tech.root: netvista
ms.assetid: FC801FA3-699F-4EE5-BED9-35CA696A5E52
ms.date: 04/08/2019
ms.keywords: "*PNDIS_WWAN_DEVICE_CAPS_EX, NDIS_WWAN_DEVICE_CAPS_EX, NDIS_WWAN_DEVICE_CAPS_EX structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_CAPS_EX, PNDIS_WWAN_DEVICE_CAPS_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_CAPS_EX, ndiswwan/NDIS_WWAN_DEVICE_CAPS_EX, ndiswwan/PNDIS_WWAN_DEVICE_CAPS_EX, netvista.ndis_wwan_device_caps_ex"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_DEVICE_CAPS_EX"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
- NDIS_WWAN_DEVICE_CAPS_EX
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_CAPS_EX, *PNDIS_WWAN_DEVICE_CAPS_EX
---

# _NDIS_WWAN_DEVICE_CAPS_EX structure


## -description


The <b>NDIS_WWAN_DEVICE_CAPS_EX</b> structure represents the capabilities of the MB device. <b>NDIS_WWAN_DEVICE_CAPS_EX</b> extends the capability of the existing <b>NDIS_WWAN_DEVICE_CAPS</b> structure by changing its <b>WWAN_DEVICE_CAPS</b> structure to a <b>WWAN_DEVICE_CAPS_EX</b> structure.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_DEVICE_CAPS_EX</b> structure.
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
Miniport drivers in Windows 10, version 1903 that support 5G set this to NDIS_WWAN_DEVICE_CAPS_EX_REVISION_2. Miniport drivers in earlier versions of Windows or that do not support 5G set this to NDIS_WWAN_DEVICE_CAPS_EX_REVISION_1.

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_CAPS_EX)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


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
The operation failed to retrieve the capabilities for the device.

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

 




#### - DeviceCapsEx

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps_ex">WWAN_DEVICE_CAPS_EX</a> structure that has an <b>ExecutorIndex</b> member and Microsoft service extension member added to the existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndiswwan/ns-ndiswwan-_ndis_wwan_device_caps">NDIS_WWAN_DEVICE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-caps-ex">OID_WWAN_DEVICE_CAPS_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps_ex">WWAN_DEVICE_CAPS_EX</a>
 

 

