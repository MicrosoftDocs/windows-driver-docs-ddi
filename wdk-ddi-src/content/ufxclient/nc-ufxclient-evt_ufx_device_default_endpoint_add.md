---
UID: NC:ufxclient.EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD (ufxclient.h)
description: The client driver's implementation to create a default control endpoint.
old-location: buses\evt_ufx_device_default_endpoint_add.htm
tech.root: usbref
ms.assetid: 37AF38A2-F761-4DBC-A7E7-FC4BDA544A31
ms.date: 05/07/2018
ms.keywords: EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD, EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback, EvtUfxDeviceDefaultEndpointAdd, EvtUfxDeviceDefaultEndpointAdd callback function [Buses], PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD, PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function pointer [Buses], buses.evt_ufx_device_default_endpoint_add, ufxclient/EvtUfxDeviceDefaultEndpointAdd
ms.topic: callback
f1_keywords:
 - "ufxclient/PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ufxclient.h
api_name:
- PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function


## -description


The client driver's implementation to create a default control endpoint.


## -parameters












#### - EndpointInit [in, out]

A pointer to an  UFXENDPOINT_INIT opaque structure that contains the endpoint descriptor required  to create an endpoint object.


#### - MaxPacketSize [in]

The default maximum packet size that can be sent from or to this endpoint.


#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</i> implementation with the USB function class extension (UFX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> method.

To create the endpoint the client driver is expected to initialize the attributes of the endpoint’s transfer and command queues, and then call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a> to create the endpoint.  After the default control endpoint is created, UFX is ready to process setup packets and other control transfer packets from host.  

The client driver indicates completion of this event by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD UfxDevice_EvtDeviceDefaultEndpointAdd;

VOID
UfxDevice_EvtDeviceDefaultEndpointAdd (
    _In_ UFXDEVICE UfxDevice,
    _In_ USHORT MaxPacketSize,
    _Inout_ PUFXENDPOINT_INIT EndpointInit
    )
/*++

Routine Description:

    EvtDeviceDefaultEndpointAdd handler for the UFXDEVICE object.
    Creates UFXENDPOINT object corresponding to the default endpoint of the
    device.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    MaxPacketSize - Max packet size of the device's default endpoint.

    EndpointInit - Pointer to the Opaque UFXENDPOINT_INIT object

--*/
{
    NTSTATUS Status;
    USB_ENDPOINT_DESCRIPTOR Descriptor;

    PAGED_CODE();

    TraceEntry();

    Descriptor.bDescriptorType = USB_ENDPOINT_DESCRIPTOR_TYPE;
    Descriptor.bEndpointAddress = 0;
    Descriptor.bInterval = 0;
    Descriptor.bLength = sizeof(USB_ENDPOINT_DESCRIPTOR);
    Descriptor.bmAttributes = USB_ENDPOINT_TYPE_CONTROL;
    Descriptor.wMaxPacketSize = MaxPacketSize;

    // #### TODO: Insert code to add the endpoint. 
    // See code example for EVT_UFX_DEVICE_ENDPOINT_ADD ####

End:
    UfxDeviceEventComplete(UfxDevice, Status);
    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a>
 

 

