---
UID: NF:netconfiguration.NetConfigurationQueryMultiString
title: NetConfigurationQueryMultiString function
author: windows-driver-content
description: Retrieves the MultiString-valued registry entry associated with a value name in the specified configuration object.
ms.assetid: a6cd726e-8c85-4a5b-9d14-986848749556
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetConfigurationQueryMultiString
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netconfiguration.h
apiname: 
-	NetConfigurationQueryMultiString
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetConfigurationQueryMultiString function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the MultiString-valued registry entry associated with a value name in the specified configuration object.

## -parameters

### -param Configuration
Handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName
A pointer to a [**UNICODE_STRING**](../wudfwdm/ns-wudfwdm-_unicode_string.md) structure that contains a value name in the device's software key.

### -param StringsAttributes
A pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains driver-supplied attributes for the new WDFSTRING objects. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Collection
A handle to a driver-supplied collection object. If the method succeeds, contains a WDFSTRING object for each string assigned to *ValueName*.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. If the registry value is NULL, **NetConfigurationQueryMultiString** returns **STATUS_OBJECT_NAME_NOT_FOUND**.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

By default, the strings are parented to the collection object. The client driver can change this by setting the **ParentObject** member of the [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure.



## -see-also