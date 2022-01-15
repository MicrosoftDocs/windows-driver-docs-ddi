---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to add a new default endpoint for a USB device.
old-location: buses\evt_ucx_usbdevice_default_endpoint_add.htm
tech.root: usbref
ms.date: 01/14/2022
keywords: ["EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function"]
ms.keywords: EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD, EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback, EvtUcxUsbDeviceDefaultEndpointAdd, EvtUcxUsbDeviceDefaultEndpointAdd callback function [Buses], PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD, PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function pointer [Buses], buses.evt_ucx_usbdevice_default_endpoint_add, ucxusbdevice/EvtUcxUsbDeviceDefaultEndpointAdd
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
 - ucxusbdevice/EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxusbdevice.h
api_name:
 - EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
---

# EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function

## -description

The client driver's implementation that UCX calls to add a new default endpoint for a USB device.

## -parameters

### -param UcxController [in]

A handle to the UCX controller that the client driver received in a previous call to  the [UcxControllerCreate](../ucxcontroller/nf-ucxcontroller-ucxcontrollercreate.md) method.

### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device.

### -param MaxPacketSize [in]

Maximum packet size for transfers on this endpoint.

### -param UcxEndpointInit [in]

A pointer to an opaque structure containing initialization information. Callbacks for the endpoint object are associated with this structure. This structure is managed by UCX.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the [UcxUsbDeviceCreate](nf-ucxusbdevice-ucxusbdevicecreate.md) method.

The callback function calls [UcxEndpointCreate](../ucxendpoint/nf-ucxendpoint-ucxendpointcreate.md) to create a new default endpoint object and register its default endpoint object callback functions.

Then, the callback function typically creates a WDF queue associated with the endpoint object. The  queue does not receive any requests until the class extension starts it.

### Examples

```cpp
NTSTATUS
Endpoint_EvtUcxUsbDeviceDefaultEndpointAdd(
    UCXCONTROLLER           UcxController,
    UCXUSBDEVICE            UcxUsbDevice,
    ULONG                   MaxPacketSize,
    PUCXENDPOINT_INIT       EndpointInit
)

{
    NTSTATUS                                status = STATUS_SUCCESS;

    UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS    ucxDefaultEndpointEventCallbacks;
    WDF_OBJECT_ATTRIBUTES                   objectAttributes;

    PUCX_CONTROLLER_CONTEXT                 ucxControllerContext;

    UCXENDPOINT                             ucxEndpoint;
    PUCX_ENDPOINT_CONTEXT                   ucxEndpointContext;


    WDF_IO_QUEUE_CONFIG                     queueConfig;
    WDFQUEUE                                wdfQueue;


    UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT(&ucxDefaultEndpointEventCallbacks,
                                              Endpoint_EvtUcxEndpointPurge,
                                              Endpoint_EvtUcxEndpointStart,
                                              Endpoint_EvtUcxEndpointAbort,
                                              Endpoint_EvtUcxEndpointOkToCancelTransfers,
                                              Endpoint_EvtUcxDefaultEndpointUpdate);

    UcxDefaultEndpointInitSetEventCallbacks(EndpointInit, &ucxDefaultEndpointEventCallbacks);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&objectAttributes, UCX_ENDPOINT_CONTEXT);

    ucxControllerContext = GetUcxControllerContext(UcxController);

    status = UcxEndpointCreate(UcxUsbDevice,
        &EndpointInit,
        &objectAttributes,
        &ucxEndpoint);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "UcxEndpoint Failed %!STATUS!", status);
        goto EvtUsbDeviceDefaultEndpointAddEnd;
    }

    DbgTrace(TL_INFO, Endpoint, "UcxEndpoint created");

    ucxEndpointContext = GetUcxEndpointContext(ucxEndpoint);

    ucxEndpointContext->IsDefault = TRUE;
    ucxEndpointContext->MaxPacketSize = MaxPacketSize;

    WDF_IO_QUEUE_CONFIG_INIT(&queueConfig, WdfIoQueueDispatchManual);

    status = WdfIoQueueCreate(ucxControllerContext->WdfDevice,
        &queueConfig,
        WDF_NO_OBJECT_ATTRIBUTES,
        &wdfQueue);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "WdfIoQueueCreate Failed %!STATUS!", status);
        goto EvtUsbDeviceDefaultEndpointAddEnd;
    }

    UcxEndpointSetWdfIoQueue(ucxEndpoint, wdfQueue);

EvtUsbDeviceDefaultEndpointAddEnd:

    return status;
}
```

## -see-also

- [UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT](../ucxendpoint/nf-ucxendpoint-ucx_default_endpoint_event_callbacks_init.md)
- [UcxDefaultEndpointInitSetEventCallbacks](../ucxendpoint/nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks.md)
- [UcxEndpointCreate](../ucxendpoint/nf-ucxendpoint-ucxendpointcreate.md)
- [UcxUsbDeviceCreate](nf-ucxusbdevice-ucxusbdevicecreate.md)
- [WDF_IO_QUEUE_CONFIG_INIT](../wdfio/nf-wdfio-wdf_io_queue_config_init.md)
- [WdfIoQueueCreate](../wdfio/nf-wdfio-wdfioqueuecreate.md)
