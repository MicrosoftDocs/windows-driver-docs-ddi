---
UID: NF:netconfiguration.NetConfigurationQueryUlong
title: NetConfigurationQueryUlong function (netconfiguration.h)
description: Retrieves the specified unsigned long word (REG_DWORD) data from the adapter configuration object and copies the data to a specified location.
tech.root: netvista
ms.assetid: c7ded93c-b025-4b23-b999-fe5d2ed0d75b
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetConfigurationQueryUlong
req.header: netconfiguration.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
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
- NetConfigurationQueryUlong
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationQueryUlong function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the specified unsigned long word (REG_DWORD) data from the adapter configuration object and copies the data to a specified location.

## -parameters

### -param Configuration
Handle to a NETCONFIGURATION object that represents an opened registry key.

### -param Flags
A valid bitwise OR of [NET_CONFIGURATION_QUERY_ULONG_FLAGS](ne-netconfiguration-_net_configuration_query_ulong_flags.md)-typed flags.

### -param ValueName
A pointer to a [**UNICODE_STRING**](../wudfwdm/ns-wudfwdm-_unicode_string.md) structure that contains a name for the ULONG value.

### -param Value
A pointer to a location that receives the data that is assigned to the value that *ValueName* specifies.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).



## -see-also
