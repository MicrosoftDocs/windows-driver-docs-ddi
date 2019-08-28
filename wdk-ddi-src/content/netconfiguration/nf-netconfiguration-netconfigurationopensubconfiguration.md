---
UID: NF:netconfiguration.NetConfigurationOpenSubConfiguration
title: NetConfigurationOpenSubConfiguration function (netconfiguration.h)
description: Opens a sub configuration of a specified adapter configuration object.
tech.root: netvista
ms.assetid: e825d2f8-b8ad-4488-a68e-73d1d6b849bb
ms.date: 02/07/2018
ms.topic: function
f1_keywords:
 - "netconfiguration/NetConfigurationOpenSubConfiguration"
ms.keywords: NetConfigurationOpenSubConfiguration
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
- NetConfigurationOpenSubConfiguration
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationOpenSubConfiguration function


## -description



Opens a sub configuration of a specified adapter configuration object.

## -parameters

### -param Configuration
A handle to an adapter configuration object opened in a prior call to [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or **NetConfigurationOpenSubConfiguration**.

### -param SubConfigurationName
A pointer to a string specifying the name of the sub configuration to open.

### -param SubConfigurationAttributes
A pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains driver-supplied attributes for the new configuration object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param SubConfiguration
A pointer to a location that receives a handle to the new sub configuration object.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
If the client provides a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md), it specifies **NULL** for **ParentObject**. By default, the sub configuration is parented to the existing adapter configuration object.

The client driver closes the sub configuration by calling [NetConfigurationClose](nf-netconfiguration-netconfigurationclose.md) with either the sub configuration object or the parent adapter configuration object.



## -see-also

[NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md)

[NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md)
