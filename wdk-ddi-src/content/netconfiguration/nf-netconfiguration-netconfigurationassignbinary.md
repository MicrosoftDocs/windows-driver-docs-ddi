---
UID: NF:netconfiguration.NetConfigurationAssignBinary
title: NetConfigurationAssignBinary function (netconfiguration.h)
description: The NetConfigurationAssignBinary method writes caller-supplied binary data to a specified value name in the registry.
tech.root: netvista
ms.assetid: 55f386f7-0327-4cd2-96bc-bb666a2b3465
ms.date: 02/07/2018
ms.topic: function
f1_keywords:
 - "netconfiguration/NetConfigurationAssignBinary"
ms.keywords: NetConfigurationAssignBinary
req.header: netconfiguration.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netconfiguration.h
api_name: 
- NetConfigurationAssignBinary
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationAssignBinary function


## -description



The **NetConfigurationAssignBinary** method writes caller-supplied binary data to a specified value name in the registry.

## -parameters

### -param Configuration
A handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName
A pointer to a [**UNICODE_STRING**](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains a value name.

### -param Buffer
A pointer to a buffer that contains driver-supplied data.

### -param BufferLength
The length, in bytes, of the buffer to which *Buffer* points.

## -returns
This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

If an entry of the same name as *ValueName* already exists under the opened registry key, **NetConfigurationAssignBinary** replaces its current value with the caller-supplied value. Otherwise, **NetConfigurationAssignBinary** adds a new value entry with the given name and supplied value to the registry.



## -see-also
