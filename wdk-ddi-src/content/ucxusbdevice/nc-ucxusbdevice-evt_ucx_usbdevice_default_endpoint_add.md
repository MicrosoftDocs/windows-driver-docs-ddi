---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls to add a new default endpoint for a USB device.
old-location: buses\evt_ucx_usbdevice_default_endpoint_add.htm
old-project: UsbRef
ms.assetid: b9c38199-810a-462b-a805-9751de2a419e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.evt_ucx_usbdevice_default_endpoint_add, EvtUcxUsbDeviceDefaultEndpointAdd callback function [Buses], EvtUcxUsbDeviceDefaultEndpointAdd, EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD, EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD, ucxusbdevice/EvtUcxUsbDeviceDefaultEndpointAdd, PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function pointer [Buses], PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxusbdevice.h
apiname:
-	PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_INFO, STREAM_INFO"
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback


## -description


The client driver's implementation that UCX calls to add a new default endpoint for a USB device.


## -prototype


````
EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD EvtUcxUsbDeviceDefaultEndpointAdd;

NTSTATUS EvtUcxUsbDeviceDefaultEndpointAdd(
  _In_ UCXCONTROLLER     UcxController,
  _In_ UCXUSBDEVICE      UcxUsbDevice,
  _In_ ULONG             MaxPacketSize,
  _In_ PUCXENDPOINT_INIT EndpointInit
)
{ ... }

typedef EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device.


### -param MaxPacketSize [in]

Maximum packet size for transfers on this endpoint.


### -param UcxEndpointInit








#### - EndpointInit [in]

A pointer to an opaque structure containing initialization
        information.  Callbacks for the endpoint object are associated with this
        structure.  This structure is managed by UCX.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

The callback function calls <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a> to create a new default endpoint object and register its default endpoint object callback functions.

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


    UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT(&amp;ucxDefaultEndpointEventCallbacks,
                                              Endpoint_EvtUcxEndpointPurge,
                                              Endpoint_EvtUcxEndpointStart,
                                              Endpoint_EvtUcxEndpointAbort,
                                              Endpoint_EvtUcxEndpointOkToCancelTransfers,
                                              Endpoint_EvtUcxDefaultEndpointUpdate,
                                              Endpoint_EvtUcxEndpointEnableForwardProgress);

    UcxDefaultEndpointInitSetEventCallbacks(EndpointInit, &amp;ucxDefaultEndpointEventCallbacks);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;objectAttributes, UCX_ENDPOINT_CONTEXT);

    ucxControllerContext = GetUcxControllerContext(UcxController);

    status = UcxEndpointCreate(UcxUsbDevice,
        &amp;EndpointInit,
        &amp;objectAttributes,
        &amp;ucxEndpoint);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "UcxEndpoint Failed %!STATUS!", status);
        goto EvtUsbDeviceDefaultEndpointAddEnd;
    }

    DbgTrace(TL_INFO, Endpoint, "UcxEndpoint created");

    ucxEndpointContext = GetUcxEndpointContext(ucxEndpoint);

    ucxEndpointContext-&gt;IsDefault = TRUE;
    ucxEndpointContext-&gt;MaxPacketSize = MaxPacketSize;

    WDF_IO_QUEUE_CONFIG_INIT(&amp;queueConfig, WdfIoQueueDispatchManual);

    status = WdfIoQueueCreate(ucxControllerContext-&gt;WdfDevice,
        &amp;queueConfig,
        WDF_NO_OBJECT_ATTRIBUTES,
        &amp;wdfQueue);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "WdfIoQueueCreate Failed %!STATUS!", status);
        goto EvtUsbDeviceDefaultEndpointAddEnd;
    }

    UcxEndpointSetWdfIoQueue(ucxEndpoint, wdfQueue);

EvtUsbDeviceDefaultEndpointAddEnd:

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>



<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="..\ucxendpoint\nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks.md">UcxDefaultEndpointInitSetEventCallbacks</a>



<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>



<a href="..\ucxendpoint\nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks.md">UcxDefaultEndpointInitSetEventCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

