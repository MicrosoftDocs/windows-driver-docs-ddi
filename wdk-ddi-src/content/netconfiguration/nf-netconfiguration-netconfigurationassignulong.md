---
UID: NF:netconfiguration.NetConfigurationAssignUlong
title: NetConfigurationAssignUlong function (netconfiguration.h)
description: The NetConfigurationAssignUlong method writes a caller-supplied unsigned long word value to a specified value name in the registry.
tech.root: netvista
ms.assetid: 239fbd90-5991-4f3d-a053-7c8586c2abdc
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetConfigurationAssignUlong
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
-	NetConfigurationAssignUlong
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationAssignUlong function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetConfigurationAssignUlong** method writes a caller-supplied unsigned long word value to a specified value name in the registry.

## -parameters

### -param Configuration
A handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName
A pointer to a [**UNICODE_STRING**](../wudfwdm/ns-wudfwdm-_unicode_string.md) structure that contains a value name. 

### -param Value
A ULONG value that will be assigned to the value name that *ValueName* specifies.

## -returns
This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

If an entry of the same name as *ValueName* already exists under the opened registry key, **NetConfigurationAssignUlong** replaces its current value with the caller-supplied value. Otherwise, **NetConfigurationAssignUlong** adds a new value entry with the given name and supplied value to the registry.



## -see-also
