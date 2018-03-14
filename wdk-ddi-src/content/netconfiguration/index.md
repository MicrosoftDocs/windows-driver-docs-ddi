---
UID: NA:netconfiguration
ms.assetid: 511aa490-3d63-3b72-a325-bdea5ca35ecb
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netconfiguration.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netconfiguration.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetConfigurationAssignBinary function](nf-netconfiguration-netconfigurationassignbinary.md) | The NetConfigurationAssignBinary method writes caller-supplied binary data to a specified value name in the registry. |
| [NetConfigurationAssignMultiString function](nf-netconfiguration-netconfigurationassignmultistring.md) | The NetConfigurationAssignMultiString method assigns a set of strings to a specified value name in the registry. The strings are contained in a specified collection of framework string objects. |
| [NetConfigurationAssignUlong function](nf-netconfiguration-netconfigurationassignulong.md) | The NetConfigurationAssignUlong method writes a caller-supplied unsigned long word value to a specified value name in the registry. |
| [NetConfigurationAssignUnicodeString function](nf-netconfiguration-netconfigurationassignunicodestring.md) | The NetConfigurationAssignUnicodeString method assigns a specified Unicode string to a specified value name in the registry. |
| [NetConfigurationClose function](nf-netconfiguration-netconfigurationclose.md) | Releases the handle to the registry key that is associated with an adapter configuration object and then deletes the adapter configuration object. |
| [NetConfigurationOpenSubConfiguration function](nf-netconfiguration-netconfigurationopensubconfiguration.md) | Opens a sub configuration of a specified adapter configuration object. |
| [NetConfigurationQueryBinary function](nf-netconfiguration-netconfigurationquerybinary.md) | Retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer. |
| [NetConfigurationQueryLinkLayerAddress function](nf-netconfiguration-netconfigurationquerylinklayeraddress.md) | The NetConfigurationQueryLinkLayerAddress method retrieves the software-configurable link layer address address that was stored in the registry for a NIC. |
| [NetConfigurationQueryMultiString function](nf-netconfiguration-netconfigurationquerymultistring.md) | Retrieves the MultiString-valued registry entry associated with a value name in the specified configuration object. |
| [NetConfigurationQueryString function](nf-netconfiguration-netconfigurationquerystring.md) | Retrieves the specified string value from the adapter configuration object and assigns the string to a specified framework string object. |
| [NetConfigurationQueryUlong function](nf-netconfiguration-netconfigurationqueryulong.md) | Retrieves the specified unsigned long word (REG_DWORD) data from the adapter configuration object and copies the data to a specified location. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_NET_CONFIGURATION_QUERY_ULONG_FLAGS enumeration](ne-netconfiguration-_net_configuration_query_ulong_flags.md) | The NET_CONFIGURATION_QUERY_ULONG_FLAGS enumeration is used as an input parameter to the NetConfigurationQueryUlong method. |
