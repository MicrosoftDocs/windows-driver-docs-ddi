---
UID: NS:ndiswwan._NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
title: _NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS (ndiswwan.h)
description: The NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure represents the commands supported by a device service.
old-location: netvista\ndis_wwan_enumerate_device_service_commands.htm
tech.root: netvista
ms.assetid: 9D30F8BE-C376-48FD-A76C-6069F332BC11
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure"]
ms.keywords: "*PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, ndiswwan/NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, ndiswwan/PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, netvista.ndis_wwan_enumerate_device_service_commands"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.typenames: NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS, *PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
f1_keywords:
 - _NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
 - ndiswwan/_NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
 - PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
 - ndiswwan/PNDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
 - NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
 - ndiswwan/NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
---

# _NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure


## -description

The NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS structure represents the commands supported by a device service.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS
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
NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_ENUMERATE_DEVICE_SERVICE_COMMANDS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field DeviceServiceGuid

The GUID of the device service for which commands should be enumerated.