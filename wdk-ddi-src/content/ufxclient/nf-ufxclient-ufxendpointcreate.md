---
UID: NF:ufxclient.UfxEndpointCreate
title: UfxEndpointCreate function (ufxclient.h)
description: Creates an endpoint object.
old-location: buses\ufxendpointcreate.htm
tech.root: usbref
ms.assetid: 060CADB7-AAC9-401A-9198-FC306CE74A34
ms.date: 05/07/2018
keywords: ["UfxEndpointCreate function"]
ms.keywords: UfxEndpointCreate, UfxEndpointCreate method [Buses], buses.ufxendpointcreate, ufxclient/UfxEndpointCreate
f1_keywords:
 - "ufxclient/UfxEndpointCreate"
 - "UfxEndpointCreate"
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ufxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ufxclient.h
api_name:
- UfxEndpointCreate
targetos: Windows
req.typenames: 
---

# UfxEndpointCreate function


## -description


Creates an endpoint object.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


### -param EndpointInit [in, out]

Opaque structure passed by UFX in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_endpoint_add">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_default_endpoint_add">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>.


### -param Attributes [in, optional]

A pointer to caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdf-object-attributes-init-context-type">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param TransferQueueConfig [in]

A pointer to a caller allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.  This structure must be initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a>.


### -param TransferQueueAttributes [in, optional]

A pointer to caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdf-object-attributes-init-context-type">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param CommandQueueConfig [in]

A pointer to a caller allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.  This structure must be initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a>.


### -param CommandQueueAttributes [in, optional]

A pointer to caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdf-object-attributes-init-context-type">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param UfxEndpoint [out]

A pointer to a location that receives a handle to a UFXENDPOINT object.


## -returns



If the operation is successful, the method returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



  The transfer queue handles the following IOCTLs related to endpoint transfers:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_in">IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_out">IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_transfer_in">IOCTL_INTERNAL_USBFN_TRANSFER_IN</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_transfer_in_append_zero_pkt">IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_transfer_out">IOCTL_INTERNAL_USBFN_TRANSFER_OUT</a>
</li>
</ul>

The command queue will handle the following IOCTLs:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_get_pipe_state">IOCTL_INTERNAL_USBFN_GET_PIPE_STATE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_set_pipe_state">IOCTL_INTERNAL_USBFN_SET_PIPE_STATE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxbase/ni-ufxbase-ioctl_internal_usbfn_descriptor_update">IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE</a>
</li>
</ul>
The following example shows how to create a UFXENDPOINT object and initialize its context.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UfxEndpointAdd (
    _In_ UFXDEVICE Device,
    _In_ PUSB_ENDPOINT_DESCRIPTOR Descriptor,
    _Inout_ PUFXENDPOINT_INIT EndpointInit
    )
/*++
Routine Description:

    Creates a UFXENDPOINT object, and initializes its contexts.

Parameters Description:

    Device - UFXDEVICE associated with the endpoint.

    Descriptor - Endpoint descriptor for this endpoint.

    EndpointInit - Opaque structure from UFX.

Return Value:

    STATUS_SUCCESS if successful, appropriate NTSTATUS message otherwise.
--*/
{
    NTSTATUS Status;
    WDF_OBJECT_ATTRIBUTES Attributes;
    WDF_IO_QUEUE_CONFIG TransferQueueConfig;
    WDF_OBJECT_ATTRIBUTES TransferQueueAttributes;
    WDF_IO_QUEUE_CONFIG CommandQueueConfig;
    WDF_OBJECT_ATTRIBUTES CommandQueueAttributes;
    UFXENDPOINT Endpoint;
    PUFXENDPOINT_CONTEXT EpContext;
    PUFXDEVICE_CONTEXT DeviceContext;
    UFX_ENDPOINT_CALLBACKS Callbacks;
    PENDPOINT_QUEUE_CONTEXT QueueContext;
    WDFQUEUE Queue;

    TraceEntry();

    DeviceContext = UfxDeviceGetContext(Device);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&Attributes, UFXENDPOINT_CONTEXT);
    Attributes.ExecutionLevel = WdfExecutionLevelPassive;
    Attributes.EvtCleanupCallback = UfxEndpoint_Cleanup;

    //
    // Note: Execution level needs to be passive to avoid deadlocks with WdfRequestComplete.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&TransferQueueAttributes, ENDPOINT_QUEUE_CONTEXT);
    TransferQueueAttributes.ExecutionLevel = WdfExecutionLevelPassive;
    
    WDF_IO_QUEUE_CONFIG_INIT(&TransferQueueConfig, WdfIoQueueDispatchManual);
    TransferQueueConfig.AllowZeroLengthRequests = TRUE;
    TransferQueueConfig.EvtIoStop = EndpointQueue_EvtIoStop;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&CommandQueueAttributes, ENDPOINT_QUEUE_CONTEXT);
    CommandQueueAttributes.ExecutionLevel = WdfExecutionLevelPassive;

    WDF_IO_QUEUE_CONFIG_INIT(&CommandQueueConfig, WdfIoQueueDispatchSequential);
    CommandQueueConfig.EvtIoInternalDeviceControl = EvtEndpointCommandQueue;

    UFX_ENDPOINT_CALLBACKS_INIT(&Callbacks);
    UfxEndpointInitSetEventCallbacks(EndpointInit, &Callbacks);

    Status = UfxEndpointCreate(
                 Device,
                 EndpointInit,
                 &Attributes,
                 &TransferQueueConfig,
                 &TransferQueueAttributes,
                 &CommandQueueConfig,
                 &CommandQueueAttributes,
                 &Endpoint);
    CHK_NT_MSG(Status, "Failed to create ufxendpoint!");

    Status = WdfCollectionAdd(DeviceContext->Endpoints, Endpoint);
    CHK_NT_MSG(Status, "Failed to add endpoint to collection!");

    EpContext = UfxEndpointGetContext(Endpoint);
    EpContext->UfxDevice = Device;
    EpContext->WdfDevice = DeviceContext->FdoWdfDevice;
    RtlCopyMemory(&EpContext->Descriptor, Descriptor, sizeof(*Descriptor));

    Queue = UfxEndpointGetTransferQueue(Endpoint);
    QueueContext = EndpointQueueGetContext(Queue);
    QueueContext->Endpoint = Endpoint;

    Queue = UfxEndpointGetCommandQueue(Endpoint);
    QueueContext = EndpointQueueGetContext(Queue);
    QueueContext->Endpoint = Endpoint;

    Status = TransferInitialize(Endpoint);
    CHK_NT_MSG(Status, "Failed to initialize endpoint transfers");
    
    //
    // This can happen if we're handling a SetInterface command.
    //
    if (DeviceContext->UsbState == UsbfnDeviceStateConfigured) {
        UfxEndpointConfigure(Endpoint);
    }

    Status = WdfIoQueueReadyNotify(
                 UfxEndpointGetTransferQueue(Endpoint),
                 TransferReadyNotify,
                 Endpoint);
    CHK_NT_MSG(Status, "Failed to register ready notify");

End:
    TraceExit();
    return Status;
}
</pre>
</td>
</tr>
</table></span></div>


