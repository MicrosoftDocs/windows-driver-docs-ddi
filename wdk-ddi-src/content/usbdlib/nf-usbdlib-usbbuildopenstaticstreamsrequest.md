---
UID: NF:usbdlib.UsbBuildOpenStaticStreamsRequest
title: UsbBuildOpenStaticStreamsRequest function
author: windows-driver-content
description: The UsbBuildOpenStaticStreamsRequest inline function formats an URB structure for an open-streams request. The request opens streams associated with the specified bulk endpoint.
old-location: buses\usbbuildopenbasicstreamsrequest.htm
old-project: UsbRef
ms.assetid: B514B88E-2D1F-43F1-BF70-BC49294CFE93
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UsbBuildOpenStaticStreamsRequest, buses.usbbuildopenbasicstreamsrequest, UsbBuildOpenStaticStreamsRequest function [Buses], usbdlib/UsbBuildOpenStaticStreamsRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbdlib.h
apiname:
-	UsbBuildOpenStaticStreamsRequest
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# UsbBuildOpenStaticStreamsRequest function


## -description


The <b>UsbBuildOpenStaticStreamsRequest</b> inline function formats an <a href="..\usb\ns-usb-_urb.md">URB</a> structure for an open-streams request. The request opens streams associated with the specified bulk endpoint.


## -syntax


````
void UsbBuildOpenStaticStreamsRequest(
  _Inout_ PURB                    Urb,
  _In_    USBD_PIPE_HANDLE        PipeHandle,
  _In_    USHORT                  NumberOfStreams,
  _In_    USBD_STREAM_INFORMATION StreamInfoArray
);
````


## -parameters




### -param Urb [in, out]

Pointer to the <a href="..\usb\ns-usb-_urb.md">URB</a> structure to be formatted for the open-stream request (URB_FUNCTION_OPEN_STATIC_STREAMS). The caller must allocate nonpaged pool for this <b>URB</b>.




### -param PipeHandle [in]

An opaque handle for the pipe associated with the endpoint that contains the streams to open.

The client driver obtains <b>PipeHandle</b> from a previous select-configuration request (URB_FUNCTION_SELECT_CONFIGURATION) or a select-interface request (URB_FUNCTION_SELECT_INTERFACE). 


### -param NumberOfStreams [in]

The number of streams to open. The <b>NumberOfStreams</b> value indicates the number of elements in the array pointed to by <b>Streams</b>. This value must be greater than zero and less than or equal to the maximum number of streams supported by the host controller hardware. To get the maximum number of supported streams, call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a>. 

The number streams must also be less than or equal to the maximum number of streams supported by the USB device. To get that number, inspect the endpoint companion descriptor. 

In the <b>NumberOfStreams</b> value, specify lesser of two values supported by the host controller and the USB device.


### -param StreamInfoArray [in]

Pointer to a caller-allocated, initialized array of <a href="..\usb\ns-usb-_usbd_stream_information.md">USBD_STREAM_INFORMATION</a> structures. The length of the array depends on the number of streams to open and must be the same as the <b>NumberOfStreams</b> value.


## -returns



This function does not return a value.




## -remarks



For a code example that shows the URB format required for an open-streams request, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.




## -see-also

<a href="..\usb\ns-usb-_urb_open_static_streams.md">_URB_OPEN_STATIC_STREAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UsbBuildOpenStaticStreamsRequest function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

