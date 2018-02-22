---
UID: NS:usbscan._USBSCAN_PIPE_INFORMATION
title: "_USBSCAN_PIPE_INFORMATION"
author: windows-driver-content
description: The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a USBSCAN_PIPE_CONFIGURATION structure.
old-location: image\usbscan_pipe_information.htm
old-project: Image
ms.assetid: a13bec15-67e1-45f9-be90-dee5c555ad64
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_USBSCAN_PIPE_INFORMATION, USBSCAN_PIPE_INFORMATION, PUSBSCAN_PIPE_INFORMATION structure pointer [Imaging Devices], PUSBSCAN_PIPE_INFORMATION, *PUSBSCAN_PIPE_INFORMATION, USBSCAN_PIPE_INFORMATION structure [Imaging Devices], image.usbscan_pipe_information, usbscan/USBSCAN_PIPE_INFORMATION, stifnc_3a31b5a2-4bd9-4e95-b10d-959c6caa8754.xml, usbscan/PUSBSCAN_PIPE_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	usbscan.h
apiname:
-	USBSCAN_PIPE_INFORMATION
product: Windows
targetos: Windows
req.typenames: USBSCAN_PIPE_INFORMATION, *PUSBSCAN_PIPE_INFORMATION
req.product: Windows 10 or later.
---

# _USBSCAN_PIPE_INFORMATION structure


## -description


The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a <a href="..\usbscan\ns-usbscan-_usbscan_pipe_configuration.md">USBSCAN_PIPE_CONFIGURATION</a> structure.


## -syntax


````
typedef struct _USBSCAN_PIPE_INFORMATION {
  USHORT        MaximumPacketSize;
  UCHAR         EndpointAddress;
  UCHAR         Interval;
  RAW_PIPE_TYPE PipeType;
} USBSCAN_PIPE_INFORMATION, *PUSBSCAN_PIPE_INFORMATION;
````


## -struct-fields




### -field MaximumPacketSize

Maximum packet size for the transfer pipe.


### -field EndpointAddress

The address of the pipe's endpoint. The address is encoded as follows:

<table>
<tr>
<th>Bits</th>
<th>Definition</th>
</tr>
<tr>
<td>
0..3

</td>
<td>
Endpoint number.

</td>
</tr>
<tr>
<td>
4..6

</td>
<td>
Reserved, set to 0.

</td>
</tr>
<tr>
<td>
7

</td>
<td>
Direction, ignored for control endpoints:

0 - OUT endpoint

1 - IN endpoint

</td>
</tr>
</table>
 

For more information, see the <i>Universal Serial Bus Specification</i>.


### -field Interval

Polling interval, in milliseconds, for interrupt pipes. For more information, see the <i>Universal Serial Bus Specification</i>.


### -field PipeType

A <a href="..\usbscan\ne-usbscan-_raw_pipe_type.md">RAW_PIPE_TYPE</a>-typed value identifying the pipe type.


## -see-also

<a href="..\usbscan\ns-usbscan-_usbscan_pipe_configuration.md">USBSCAN_PIPE_CONFIGURATION</a>



<a href="..\usbscan\ne-usbscan-_raw_pipe_type.md">RAW_PIPE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20USBSCAN_PIPE_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

