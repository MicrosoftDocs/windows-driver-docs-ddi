---
UID: NF:netrequestqueue.NetRequestQueueCreate
title: NetRequestQueueCreate function (netrequestqueue.h)
description: Creates a net request queue object.
tech.root: netvista
ms.assetid: 43552ec5-82e4-4ba8-af21-900c32c782b7
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRequestQueueCreate
req.header: netrequestqueue.h
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
- apiref
apitype: 
- HeaderDef
apilocation: 
- netrequestqueue.h
apiname: 
- NetRequestQueueCreate
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRequestQueueCreate function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Creates a net request queue object.

## -parameters

### -param NetRequestQueueConfig
A pointer to a caller-allocated [NET_REQUEST_QUEUE_CONFIG](ns-netrequestqueue-_net_request_queue_config.md) structure.

### -param QueueAttributes
An optional pointer to a caller-allocated [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that specifies attributes for the net request queue object.

### -param Queue
An optional pointer to a location that receives a handle to the new net request queue object.

## -returns
This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver typically calls this method from its *[EvtDriverDeviceAdd](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)* routine after the client has called [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md) and [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

The NETREQUESTQUEUE object represents an OID queue in the traditional NDIS model.



### Example
Typically, the client creates a queue for regular (sequential) OIDs, and may optionally also create a second queue for direct (parallel) OIDs. This example shows how to create a sequential queue. Error handling has been omitted for clarify.

```c++
    NET_REQUEST_QUEUE_CONFIG config;

    // Initialize the Queue Config
    NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL(&config,
                                                     AdapterContext->GetNetAdapter());

    //
    // Register default handlers as needed
    //
    config.EvtRequestDefaultSetData = EvtNetRequestSetData;
    config.EvtRequestDefaultQueryData = EvtNetRequestQueryData;
    config.EvtRequestDefaultMethod = EvtNetRequestMethod;

    //
    // Add custom request handlers as needed
    //
    ...

    //
    // Create the default NETREQUESTQUEUE
    //
    status = NetRequestQueueCreate(&config,
                                   WDF_NO_OBJECT_ATTRIBUTES,
                                   NULL);
```

## -see-also

[NET_REQUEST_QUEUE_CONFIG_ADD_METHOD_HANDLER](nf-netrequestqueue-net_request_queue_config_add_method_handler.md)

[NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_query_data_handler.md)

[NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_set_data_handler.md)

[NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_PARALLEL](nf-netrequestqueue-net_request_queue_config_init_default_parallel.md)

[NET_REQUEST_QUEUE_CONFIG_INIT_DEFAULT_SEQUENTIAL](nf-netrequestqueue-net_request_queue_config_init_default_sequential.md)
