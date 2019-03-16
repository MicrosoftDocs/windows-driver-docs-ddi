---
UID: NS:usb._URB_OPEN_STATIC_STREAMS
title: _URB_OPEN_STATIC_STREAMS (usb.h)
description: The _URB_OPEN_STATIC_STREAMS structure is used by a USB client driver to open streams in the specified bulk endpoint.
old-location: buses\_urb_open_basic_streams.htm
tech.root: usbref
ms.assetid: B3C329D6-541B-410D-A9AB-AF91F1141DFD
ms.date: 05/07/2018
ms.keywords: "_URB_OPEN_STATIC_STREAMS, _URB_OPEN_STATIC_STREAMS structure [Buses], buses._urb_open_basic_streams, usb/_URB_OPEN_STATIC_STREAMS"
ms.topic: struct
req.header: usb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usb.h
api_name:
- _URB_OPEN_STATIC_STREAMS
product:
- Windows
targetos: Windows
req.typenames: 
---

# _URB_OPEN_STATIC_STREAMS structure


## -description


The <b>_URB_OPEN_STATIC_STREAMS</b> structure is used by a  USB client driver to open streams in the specified bulk endpoint. 

To format the URB, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406226">UsbBuildOpenStaticStreamsRequest</a>  function.


## -struct-fields




### -field Hdr

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_OPEN_STATIC_STREAMS, and <b>Hdr.Length</b> must be <code>sizeof(_URB_OPEN_STATIC_STREAMS)</code>.



### -field PipeHandle

An opaque handle for the pipe associated with the endpoint that supports the streams to open.

The client driver obtains <b>PipeHandle</b> from the    URB_FUNCTION_SELECT_CONFIGURATION or URB_FUNCTION_SELECT_INTERFACE request. 


### -field NumberOfStreams

The number of streams to open. The <b>NumberOfStreams</b> value indicates the number of elements in the array pointed to by <b>Streams</b>. This value must be greater than zero and less than or equal to the maximum number of streams supported by the USB driver stack, the host controller, and the endpoint in the device. For more information, see Remarks.


### -field StreamInfoVersion

Version of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406247">USBD_STREAM_INFORMATION</a> structure.  Must be set to URB_OPEN_STATIC_STREAMS_VERSION_100; otherwise, the request fails and the URB status is  USBD_STATUS_INVALID_PARAMETER.


### -field StreamInfoSize

Size of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406247">USBD_STREAM_INFORMATION</a> structure.  <b>StreamInfoSize</b> must be <code>sizeof(USBD_STREAM_INFORMATION)</code>;
otherwise, the request fails and the URB status is  USBD_STATUS_INFO_LENGTH_MISMATCH.  


### -field Streams

Pointer to a caller-allocated, initialized array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406247">USBD_STREAM_INFORMATION</a> structures. The length of the array depends on the number of streams to open and must be the same as the <b>NumberOfStreams</b> value.   For more information, see Remarks. 
 
 



## -remarks



To use  streams (other than the default stream) in the endpoint for I/O operations, the client driver opens the required streams by sending an open-stream request (URB_FUNCTION_OPEN_STATIC_STREAMS) to the USB driver stack. For the request, the client driver must format the URB by  initializing the  <b>_URB_OPEN_STATIC_STREAMS</b> structure. To format the URB, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406226">UsbBuildOpenStaticStreamsRequest</a>  function.

The maximum number of streams that can be opened by a client driver, must be less than or equal to the maximum number of streams supported by the USB driver stack, the host controller, and the bulk endpoint. To get the maximum number of streams supported by the host controller, call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a>. The USB driver stack supports up to 255 streams.  If the client driver requests more than 255 streams, <b>USBD_QueryUsbCapability</b> fails the request. To get the maximum number of streams supported by the endpoint, inspect the endpoint companion descriptor (see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406269">USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</a> in Usbspec.h).

For information about formatting the URB for the open-stream request and code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.

When the client driver is finished using the streams, the driver can close all streams associated with a particular endpoint by sending a close-stream request. To send the request, the client driver must specify information about the endpoint in  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540419">_URB_PIPE_REQUEST</a> structure. The <b>Hdr</b> member of <b>_URB_PIPE_REQUEST</b> must be URB_FUNCTION_CLOSE_STATIC_STREAMS; the <b>PipeHandle</b> member must be the handle to the endpoint that contains the  streams in use. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>
 

 

