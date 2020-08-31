---
UID: NF:netadapter.NetAdapterOpenConfiguration
title: NetAdapterOpenConfiguration function (netadapter.h)
description: Opens the adapter’s configuration database.
tech.root: netvista
ms.assetid: 42e2310c-2302-4594-96ab-574e13f99a6c
ms.date: 02/06/2018
keywords: ["NetAdapterOpenConfiguration function"]
ms.keywords: NetAdapterOpenConfiguration
req.header: netadapter.h
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
req.typenames: NetAdapterOpenConfiguration
targetos: Windows
f1_keywords:
 - NetAdapterOpenConfiguration
 - netadapter/NetAdapterOpenConfiguration
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NetAdapterOpenConfiguration
---

# NetAdapterOpenConfiguration function


## -description

The **NetAdapterOpenConfiguration** function opens a net adapter’s configuration database.

## -parameters

### -param Adapter

The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param ConfigurationAttributes

A pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains driver-supplied attributes for the new configuration object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Configuration

A pointer to a location that receives a handle to the new adapter configuration object.

## -returns

The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

Typically, the client calls this function from its *[EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)* callback function.

If the client provides a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md), it specifies **NULL** for **ParentObject**. The adapter configuration object is automatically parented to the adapter object.

As a result, WDF automatically deletes the configuration object when the adapter is deleted. However, the client can manually delete a configuration object by calling [WdfObjectDelete](../wdfobject/nf-wdfobject-wdfobjectdelete.md), typically from its *[EVT_WDF_OBJECT_CONTEXT_CLEANUP](../wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup.md)* callback function.

## -see-also

[Accessing configuration information](https://docs.microsoft.com/windows-hardware/drivers/netcx/accessing-configuration-information)

[NetConfigurationClose](../netconfiguration/nf-netconfiguration-netconfigurationclose.md)

