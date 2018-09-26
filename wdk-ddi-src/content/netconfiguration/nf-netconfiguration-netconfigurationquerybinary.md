---
UID: NF:netconfiguration.NetConfigurationQueryBinary
title: NetConfigurationQueryBinary function
author: windows-driver-content
description: Retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.
tech.root: netvista
ms.assetid: bc8e68be-3bbd-47b6-ba9a-1ab1ee063b39
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetConfigurationQueryBinary
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netconfiguration.h
apiname: 
-	NetConfigurationQueryBinary
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationQueryBinary function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.

## -parameters

### -param Configuration
Handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName
A pointer to a [**UNICODE_STRING**](../wudfwdm/ns-wudfwdm-_unicode_string.md) structure that contains a value name. 

### -param PoolType
A **POOL_TYPE**-typed value that specifies the type of memory to be allocated for the data buffer. 

### -param MemoryAttributes
A pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 

### -param Memory
A pointer to a location that receives a handle to the new memory object. 

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).



## -see-also
