---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ENDPOINT_ADD
title: EVT_UCX_USBDEVICE_ENDPOINT_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls to add a new endpoint for a USB device.
old-location: buses\evt_ucx_usbdevice_endpoint_add.htm
old-project: usbref
ms.assetid: 1cbafa33-e957-4865-9d4f-26f12827a941
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UCX_USBDEVICE_ENDPOINT_ADD, EvtUcxUsbDeviceEndpointAdd, EvtUcxUsbDeviceEndpointAdd callback function [Buses], PEVT_UCX_USBDEVICE_ENDPOINT_ADD, PEVT_UCX_USBDEVICE_ENDPOINT_ADD callback function pointer [Buses], buses.evt_ucx_usbdevice_endpoint_add, ucxusbdevice/EvtUcxUsbDeviceEndpointAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxusbdevice.h
api_name:
-	PEVT_UCX_USBDEVICE_ENDPOINT_ADD
product:
- Windows
targetos: Windows
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_ENDPOINT_ADD callback


## -description


The client driver's implementation that UCX calls to add a new endpoint for a USB device.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device.


### -param UsbEndpointDescriptor [in]

A pointer to a location containing a USB descriptor for the endpoint being created.


### -param UsbEndpointDescriptorBufferLength [in]

Length in bytes of the descriptor.


### -param SuperSpeedEndpointCompanionDescriptor [in, optional]

An additional descriptor for a super speed port. This parameter is optional and may be <b>NULL</b>.


### -param UcxEndpointInit [in]

A pointer to an opaque structure containing initialization
    information.  Callbacks for the endpoint object are associated with this
    structure.  This structure is managed by UCX.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a> method.

The callback function calls <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a> to create a new endpoint object and register endpoint object callback functions.

Then, the callback  function typically creates a WDF queue associated with the endpoint
    object.   The  queue does not receive any requests until the class extension
    starts it.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Endpoint_EvtUcxUsbDeviceEndpointAdd(
    UCXCONTROLLER                                   UcxController,
    UCXUSBDEVICE                                    UcxUsbDevice,
    PUSB_ENDPOINT_DESCRIPTOR                        UsbEndpointDescriptor,
    ULONG                                           UsbEndpointDescriptorBufferLength,
    PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR   SuperSpeedEndpointCompanionDescriptor,
    PUCXENDPOINT_INIT                               UcxEndpointInit
)

{
    NTSTATUS                        status = STATUS_SUCCESS;

    UCX_ENDPOINT_EVENT_CALLBACKS    ucxEndpointEventCallbacks;
    WDF_OBJECT_ATTRIBUTES           objectAttributes;

    PUCX_CONTROLLER_CONTEXT         ucxControllerContext;

    UCXENDPOINT                     ucxEndpoint;
    PUCX_ENDPOINT_CONTEXT           ucxEndpointContext;

    WDF_IO_QUEUE_CONFIG             queueConfig;

    UNREFERENCED_PARAMETER(UsbEndpointDescriptor);
    UNREFERENCED_PARAMETER(UsbEndpointDescriptorBufferLength);
    UNREFERENCED_PARAMETER(SuperSpeedEndpointCompanionDescriptor);

    UCX_ENDPOINT_EVENT_CALLBACKS_INIT(&amp;ucxEndpointEventCallbacks,
                                      Endpoint_EvtUcxEndpointPurge,
                                      Endpoint_EvtUcxEndpointStart,
                                      Endpoint_EvtUcxEndpointAbort,
                                      Endpoint_EvtUcxEndpointReset,
                                      Endpoint_EvtUcxEndpointOkToCancelTransfers,
                                      Endpoint_EvtUcxEndpointStaticStreamsAdd,
                                      Endpoint_EvtUcxEndpointStaticStreamsEnable,
                                      Endpoint_EvtUcxEndpointStaticStreamsDisable,
                                      Endpoint_EvtUcxEndpointEnableForwardProgress);

    UcxEndpointInitSetEventCallbacks(UcxEndpointInit, &amp;ucxEndpointEventCallbacks);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;objectAttributes, UCX_ENDPOINT_CONTEXT);

    ucxControllerContext = GetUcxControllerContext(UcxController);

    status = UcxEndpointCreate(UcxUsbDevice,
        &amp;UcxEndpointInit,
        &amp;objectAttributes,
        &amp;ucxEndpoint);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "UcxEndpoint Failed %!STATUS!", status);
        goto EvtUsbDeviceEndpointAddEnd;
    }

    DbgTrace(TL_INFO, Endpoint, "UcxEndpoint created");

    ucxEndpointContext = GetUcxEndpointContext(ucxEndpoint);

    ucxEndpointContext-&gt;IsDefault = FALSE;
    ucxEndpointContext-&gt;MaxPacketSize = MAX_PACKET_SIZE;

    WDF_IO_QUEUE_CONFIG_INIT(&amp;queueConfig, WdfIoQueueDispatchManual);

    status = WdfIoQueueCreate(ucxControllerContext-&gt;WdfDevice,
        &amp;queueConfig,
        WDF_NO_OBJECT_ATTRIBUTES,
        &amp;ucxEndpointContext-&gt;IoQueue);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "WdfIoQueueCreate Failed %!STATUS!", status);
        goto EvtUsbDeviceEndpointAddEnd;
    }

    UcxEndpointSetWdfIoQueue(ucxEndpoint, ucxEndpointContext-&gt;IoQueue);

EvtUsbDeviceEndpointAddEnd:

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188037">UcxDefaultEndpointInitSetEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188052">UcxUsbDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552360">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>
 

 

