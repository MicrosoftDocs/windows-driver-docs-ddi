---
UID: NS:usbioctl._USB_PIPE_INFO
title: _USB_PIPE_INFO (usbioctl.h)
description: The USB_PIPE_INFO structure is used in conjunction with the USB_NODE_CONNECTION_INFORMATION_EX structure and the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request to obtain information about a connection and its associated pipes.
old-location: buses\usb_pipe_info.htm
tech.root: usbref
ms.assetid: 9da16cd4-bd5f-4713-83ce-4302f6807476
ms.date: 05/07/2018
ms.keywords: "*PUSB_PIPE_INFO, PUSB_PIPE_INFO, PUSB_PIPE_INFO structure pointer [Buses], USB_PIPE_INFO, USB_PIPE_INFO structure [Buses], _USB_PIPE_INFO, buses.usb_pipe_info, usbioctl/PUSB_PIPE_INFO, usbioctl/USB_PIPE_INFO, usbstrct_bba47504-f840-483c-9cf8-49a7ade717d3.xml"
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbioctl.h
api_name:
- USB_PIPE_INFO
product:
- Windows
targetos: Windows
req.typenames: USB_PIPE_INFO, *PUSB_PIPE_INFO
---

# _USB_PIPE_INFO structure


## -description


The <b>USB_PIPE_INFO</b> structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537321">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request to obtain information about a connection and its associated pipes.


## -struct-fields




### -field EndpointDescriptor

Describes the endpoint descriptor. For more information about the endpoint descriptor, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a>.


### -field ScheduleOffset

Indicates the schedule offset assigned to the endpoint for this pipe. See the remarks section for a discussion of the range of values that this member can take. 


## -remarks



The USB specification labels isochronous and interrupt transfers as "periodic," because certain periods of transmission time are set aside for these types of transfers. The port driver further divides these periods into "schedule offsets" and distributes the available offsets between those endpoints that are doing periodic transfers. The number of offsets that are available depends on the period. The following table lists the offset values that are available for each period.

<table>
<tr>
<th>Period</th>
<th>Available Offsets</th>
</tr>
<tr>
<td>
1

</td>
<td>
0

</td>
</tr>
<tr>
<td>
2

</td>
<td>
0 to 1

</td>
</tr>
<tr>
<td>
4

</td>
<td>
0 to 3

</td>
</tr>
<tr>
<td>
8

</td>
<td>
0 to 7

</td>
</tr>
<tr>
<td>
16

</td>
<td>
0 to 15 

</td>
</tr>
<tr>
<td>
32

</td>
<td>
0 to 31

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537321">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a>
 

 

