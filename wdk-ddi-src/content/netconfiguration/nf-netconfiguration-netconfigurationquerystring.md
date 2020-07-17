---
UID: NF:netconfiguration.NetConfigurationQueryString
title: NetConfigurationQueryString function (netconfiguration.h)
description: Retrieves the specified string value from the adapter configuration object and assigns the string to a specified framework string object.
tech.root: netvista
ms.assetid: 2523f6df-64d5-491d-ad0e-557896268697
ms.date: 02/07/2018
keywords: ["NetConfigurationQueryString function"]
f1_keywords:
 - "netconfiguration/NetConfigurationQueryString"
 - "NetConfigurationQueryString"
ms.keywords: NetConfigurationQueryString
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
- NetConfigurationQueryString
targetos: Windows
product:
- Windows
---

# NetConfigurationQueryString function


## -description



Retrieves the specified string value from the adapter configuration object and assigns the string to a specified framework string object.

## -parameters

### -param Configuration
Handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName
A pointer to a [**UNICODE_STRING**](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains a name for string value.

### -param StringAttributes
A pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains driver-supplied attributes for the new WDFSTRING object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param WdfString
A handle to a framework string object. NetAdapterCx will assign the registry value's string data to this object.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

By default, the framework string object is parented to the collection object. The client driver can change this by setting the **ParentObject** member of the [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure.



## -see-also
