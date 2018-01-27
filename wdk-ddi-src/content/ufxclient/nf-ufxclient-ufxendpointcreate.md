---
UID: NF:ufxclient.UfxEndpointCreate
title: UfxEndpointCreate function
author: windows-driver-content
description: Creates an endpoint object.
old-location: buses\ufxendpointcreate.htm
old-project: usbref
ms.assetid: 060CADB7-AAC9-401A-9198-FC306CE74A34
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxEndpointCreate method [Buses], ufxclient/UfxEndpointCreate, buses.ufxendpointcreate, UfxEndpointCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	ufxclient.h
apiname: 
-	UfxEndpointCreate
product: Windows
targetos: Windows
req.typenames: *PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxEndpointCreate function


## -description


Creates an endpoint object.


## -syntax


````
NTSTATUS UfxEndpointCreate(
  [in]           UFXDEVICE              UfxDevice,
  [in, out]      PUFXENDPOINT_INIT      EndpointInit,
  [in, optional] PWDF_OBJECT_ATTRIBUTES Attributes,
  [in]           PWDF_IO_QUEUE_CONFIG   TransferQueueConfig,
  [in, optional] PWDF_OBJECT_ATTRIBUTES TransferQueueAttributes,
  [in]           PWDF_IO_QUEUE_CONFIG   CommandQueueConfig,
  [in, optional] PWDF_OBJECT_ATTRIBUTES CommandQueueAttributes,
  [out]          UFXENDPOINT            *UfxEndpoint
);
````


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


### -param EndpointInit [in, out]

Opaque structure passed by UFX in the call to <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_endpoint_add.md">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_default_endpoint_add.md">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>.


### -param Attributes [in, optional]

A pointer to caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param TransferQueueConfig [in]

A pointer to a caller allocated <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.  This structure must be initialized with <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>.


### -param TransferQueueAttributes [in, optional]

A pointer to caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param CommandQueueConfig [in]

A pointer to a caller allocated <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.  This structure must be initialized with <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>.


### -param CommandQueueAttributes [in, optional]

A pointer to caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param UfxEndpoint [out]

A pointer to a location that receives a handle to a UFXENDPOINT object.


## -returns


If the operation is successful, the method returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.



## -remarks


  The transfer queue handles the following IOCTLs related to endpoint transfers:
<ul>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_in.md">IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN</a>
</li>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_out.md">IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT</a>
</li>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_transfer_in.md">IOCTL_INTERNAL_USBFN_TRANSFER_IN</a>
</li>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_transfer_in_append_zero_pkt.md">IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT</a>
</li>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_transfer_out.md">IOCTL_INTERNAL_USBFN_TRANSFER_OUT</a>
</li>
</ul>
The command queue will handle the following IOCTLs:
<ul>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_get_pipe_state.md">IOCTL_INTERNAL_USBFN_GET_PIPE_STATE</a>
</li>
<li>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_set_pipe_state.md">IOCTL_INTERNAL_USBFN_SET_PIPE_STATE</a>
</li>
<li>
<a href="..\ufxbase\ni-ufxbase-ioctl_internal_usbfn_descriptor_update.md">IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE</a>
</li>
</ul>The following example shows how to create a UFXENDPOINT object and initialize its context.
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

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;Attributes, UFXENDPOINT_CONTEXT);
    Attributes.ExecutionLevel = WdfExecutionLevelPassive;
    Attributes.EvtCleanupCallback = UfxEndpoint_Cleanup;

    //
    // Note: Execution level needs to be passive to avoid deadlocks with WdfRequestComplete.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;TransferQueueAttributes, ENDPOINT_QUEUE_CONTEXT);
    TransferQueueAttributes.ExecutionLevel = WdfExecutionLevelPassive;
    
    WDF_IO_QUEUE_CONFIG_INIT(&amp;TransferQueueConfig, WdfIoQueueDispatchManual);
    TransferQueueConfig.AllowZeroLengthRequests = TRUE;
    TransferQueueConfig.EvtIoStop = EndpointQueue_EvtIoStop;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;CommandQueueAttributes, ENDPOINT_QUEUE_CONTEXT);
    CommandQueueAttributes.ExecutionLevel = WdfExecutionLevelPassive;

    WDF_IO_QUEUE_CONFIG_INIT(&amp;CommandQueueConfig, WdfIoQueueDispatchSequential);
    CommandQueueConfig.EvtIoInternalDeviceControl = EvtEndpointCommandQueue;

    UFX_ENDPOINT_CALLBACKS_INIT(&amp;Callbacks);
    UfxEndpointInitSetEventCallbacks(EndpointInit, &amp;Callbacks);

    Status = UfxEndpointCreate(
                 Device,
                 EndpointInit,
                 &amp;Attributes,
                 &amp;TransferQueueConfig,
                 &amp;TransferQueueAttributes,
                 &amp;CommandQueueConfig,
                 &amp;CommandQueueAttributes,
                 &amp;Endpoint);
    CHK_NT_MSG(Status, "Failed to create ufxendpoint!");

    Status = WdfCollectionAdd(DeviceContext-&gt;Endpoints, Endpoint);
    CHK_NT_MSG(Status, "Failed to add endpoint to collection!");

    EpContext = UfxEndpointGetContext(Endpoint);
    EpContext-&gt;UfxDevice = Device;
    EpContext-&gt;WdfDevice = DeviceContext-&gt;FdoWdfDevice;
    RtlCopyMemory(&amp;EpContext-&gt;Descriptor, Descriptor, sizeof(*Descriptor));

    Queue = UfxEndpointGetTransferQueue(Endpoint);
    QueueContext = EndpointQueueGetContext(Queue);
    QueueContext-&gt;Endpoint = Endpoint;

    Queue = UfxEndpointGetCommandQueue(Endpoint);
    QueueContext = EndpointQueueGetContext(Queue);
    QueueContext-&gt;Endpoint = Endpoint;

    Status = TransferInitialize(Endpoint);
    CHK_NT_MSG(Status, "Failed to initialize endpoint transfers");
    
    //
    // This can happen if we're handling a SetInterface command.
    //
    if (DeviceContext-&gt;UsbState == UsbfnDeviceStateConfigured) {
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

