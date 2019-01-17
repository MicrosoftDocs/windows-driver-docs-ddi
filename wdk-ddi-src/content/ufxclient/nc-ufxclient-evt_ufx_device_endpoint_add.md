---
UID: NC:ufxclient.EVT_UFX_DEVICE_ENDPOINT_ADD
title: EVT_UFX_DEVICE_ENDPOINT_ADD
description: The client driver's implementation to create a default endpoint object.
old-location: buses\evt_ufx_device_endpoint_add.htm
tech.root: usbref
ms.assetid: F366990E-7FE3-401B-B8BE-E71EAFD3AC58
ms.date: 05/07/2018
ms.keywords: EVT_UFX_DEVICE_ENDPOINT_ADD, EVT_UFX_DEVICE_ENDPOINT_ADD callback, EvtUfxDeviceEndpointAdd, EvtUfxDeviceEndpointAdd callback function [Buses], PFN_UFX_DEVICE_ENDPOINT_ADD, PFN_UFX_DEVICE_ENDPOINT_ADD callback function pointer [Buses], buses.evt_ufx_device_endpoint_add, ufxclient/EvtUfxDeviceEndpointAdd
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_ENDPOINT_ADD
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_ENDPOINT_ADD callback function


## -description


The client driver's implementation to create a default endpoint object.


## -parameters












#### - EndpointDescriptor [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure that contains descriptor data.


#### - EndpointInit [in, out]

A pointer to an  UFXENDPOINT_INIT opaque structure that contains the endpoint descriptor required  to create an endpoint object.


#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_ENDPOINT_ADD</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

To create the endpoint the client driver is expected to initialize the attributes of the endpoint’s transfer and command queues, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a> to create the endpoint.

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_UFX_DEVICE_ENDPOINT_ADD UfxDevice_EvtDeviceEndpointAdd;

NTSTATUS
UfxDevice_EvtDeviceEndpointAdd (
    _In_ UFXDEVICE UfxDevice,
    _In_ const PUSB_ENDPOINT_DESCRIPTOR EndpointDescriptor,
    _Inout_ PUFXENDPOINT_INIT EndpointInit
    )
/*++

Routine Description:

    EvtDeviceEndpointAdd handler for the UFXDEVICE object.
    Creates UFXENDPOINT object corresponding to the newly reported endpoint.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    EndpointDescriptor - Cosntant Pointer to Endpoint descriptor for the
        newly reported endpoint.

    EndpointInit - Pointer to the Opaque UFXENDPOINT_INIT object

Return Value:

    STATUS_SUCCESS on success, or an appropirate NTSTATUS message on failure.

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


    Status = WdfCollectionAdd(DeviceContext-&gt;Endpoints, Endpoint);


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

End:
    TraceExit();
    return Status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
 

 

