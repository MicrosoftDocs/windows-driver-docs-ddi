---
UID: NC:udecxusbendpoint.EVT_UDECX_USB_ENDPOINT_PURGE
title: EVT_UDECX_USB_ENDPOINT_PURGE (udecxusbendpoint.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function to stop queuing I/O requests to the endpoint's queue and cancel unprocessed requests.
old-location: buses\evt_udecx_usb_endpoint_purge.htm
tech.root: usbref
ms.assetid: FAC021F0-CF37-4A28-BE89-D6BD77B8B708
ms.date: 05/07/2018
keywords: ["EVT_UDECX_USB_ENDPOINT_PURGE callback function"]
ms.keywords: EVT_UDECX_USB_ENDPOINT_PURGE, EVT_UDECX_USB_ENDPOINT_PURGE callback, EvtUsbEndpointPurge, EvtUsbEndpointPurge callback function [Buses], buses.evt_udecx_usb_endpoint_purge, udecxusbendpoint/EvtUsbEndpointPurge
req.header: udecxusbendpoint.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UDECX_USB_ENDPOINT_PURGE
 - udecxusbendpoint/EVT_UDECX_USB_ENDPOINT_PURGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - UdecxUsbEndpoint.h
api_name:
 - EvtUsbEndpointPurge
---

# EVT_UDECX_USB_ENDPOINT_PURGE callback function


## -description

The USB device emulation class extension (UdeCx) invokes this callback function to stop queuing I/O requests to the endpoint's queue and cancel unprocessed requests.

## -parameters

### -param UdecxUsbEndpoint 

[in]
A handle to a UDE endpoint object that represents the endpoint for which I/O requests must be canceled. The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>.

## -remarks

The client driver registered this callback function in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks">UdecxUsbEndpointInitSetCallbacks</a> by supplying a function pointer to its implementation.

In the implementation, the client driver is required to ensure all I/O forwarded from the endpoint’s queue has been completed, and that newly forwarded I/O request fail, until UdeCx invokes <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nc-udecxusbendpoint-evt_udecx_usb_endpoint_start">EVT_UDECX_USB_ENDPOINT_START</a>. Typically, those tasks are achieved by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>. This call is asynchronous and the client river must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointpurgecomplete">UdecxUsbEndpointPurgeComplete</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>

