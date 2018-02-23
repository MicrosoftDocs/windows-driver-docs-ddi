---
UID: NS:usb._USBD_STREAM_INFORMATION
title: "_USBD_STREAM_INFORMATION"
author: windows-driver-content
description: The USBD_STREAM_INFORMATION structure stores information about a stream associated with a bulk endpoint.
old-location: buses\usbd_stream_information.htm
old-project: UsbRef
ms.assetid: AFB502BF-4BC2-439E-BF1F-5D1DE3172362
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: USBD_STREAM_INFORMATION, PUSBD_STREAM_INFORMATION structure pointer [Buses], usb/PUSBD_STREAM_INFORMATION, usb/USBD_STREAM_INFORMATION, *PUSBD_STREAM_INFORMATION, buses.usbd_stream_information, PUSBD_STREAM_INFORMATION, USBD_STREAM_INFORMATION structure [Buses], _USBD_STREAM_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usb.h
apiname:
-	USBD_STREAM_INFORMATION
product: Windows
targetos: Windows
req.typenames: USBD_STREAM_INFORMATION, *PUSBD_STREAM_INFORMATION
req.product: Windows 10 or later.
---

# _USBD_STREAM_INFORMATION structure


## -description


The <b>USBD_STREAM_INFORMATION</b> structure stores information about a stream associated with a bulk endpoint.


## -syntax


````
typedef struct _USBD_STREAM_INFORMATION {
  USBD_PIPE_HANDLE PipeHandle;
  ULONG            StreamID;
  ULONG            MaximumTransferSize;
  ULONG            PipeFlags;
} USBD_STREAM_INFORMATION, *PUSBD_STREAM_INFORMATION;
````


## -struct-fields




### -field PipeHandle

An opaque handle to  the stream.


### -field StreamID

Stream identifier. The open-static streams request obtains stream identifiers that are assigned by the USB driver stack.


### -field MaximumTransferSize

Maximum transfer size (in bytes) that a client driver can send in a single URB for an I/O transfer to the stream.


### -field PipeFlags

Reserved. Do not use.


## -remarks



A client driver allocates an array of  <b>USBD_STREAM_INFORMATION</b> structures and sends it in an open-streams request (URB_FUNCTION_OPEN_STATIC_STREAMS).  Upon completion, the USB driver stack retrieves stream information and populates each <b>USBD_STREAM_INFORMATION</b> structure with stream information.  The stream identifiers returned by the request are sequential and start at 1.




## -see-also

<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>



<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="..\usb\ns-usb-_urb_open_static_streams.md">_URB_OPEN_STATIC_STREAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBD_STREAM_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

