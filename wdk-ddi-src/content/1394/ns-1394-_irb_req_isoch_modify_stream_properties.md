---
UID: NS:1394._IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES
title: _IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES
author: windows-driver-content
description: This structure contains the fields necessary for the Bus driver to carry out an IsochModifyStreamProperties request.
old-location: ieee\irb_req_isoch_modify_stream_properties.htm
old-project: IEEE
ms.assetid: 06CA5F26-8042-4EAC-A381-A0C6E7023BFD
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES, IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES
req.alt-loc: 1394.h
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
req.typenames: IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES
---

# _IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES structure



## -description
This structure contains the fields necessary for the Bus driver to carry out an <b>IsochModifyStreamProperties</b> request.
This request is used to dynamically change the properties of an allocated
resource, without the need to free and re-allocate the resource.
The resource must not be streaming when this is issued. The caller should
issue an ISOCH_STOP first and then an  ISOCH_START. Also, no buffer can be
pending after the ISOCH_STOP and before this call is made.



## -syntax

````
typedef struct _IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES {
  HANDLE         hResource;
  ULARGE_INTEGER ChannelMask;
  ULONG          fulSpeed;
} IRB_REQ_ISOCH_MODIFY_STREAM_PROPERTIES;
````


## -struct-fields

### -field hResource

The handle for the allocated resource. 


### -field ChannelMask

Specifies the allocated channel. 


### -field fulSpeed

Specifies the connection speed to use for communication on the channel.  The possible speed values are SPEED_FLAGS_xxx, where xxx is the (approximate) transfer rate in megabits per second. Existing hardware supports transfer rates of 100, 200, and 400 Mb/sec.

<table>
<tr>
<th>Transfer Rate</th>
<th>Description</th>
</tr>
<tr>
<td>
SPEED_FLAGS_100

</td>
<td>
100 Mb/s

</td>
</tr>
<tr>
<td>
SPEED_FLAGS_200

</td>
<td>
200 Mb/s

</td>
</tr>
<tr>
<td>
SPEED_FLAGS_400

</td>
<td>
400 Mb/s

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="buses.device_driver_interface__ddi__changes_in_windows_7#speed#speed">New Flags for Speed and Payload Size</a> and <a href="buses.device_driver_interface__ddi__changes_in_windows_7#ioctl#ioctl">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>

## -remarks
The resource must not be streaming when <a href="https://msdn.microsoft.com/library/windows/hardware/gg266405">REQUEST_ISOCH_MODIFY_STREAM_PROPERTIES</a>  is issued. Before issuing <b>REQUEST_ISOCH_MODIFY_STREAM_PROPERTIES</b>, the caller must  send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537659">REQUEST_ISOCH_STOP</a> request followed by a start request. Also make sure that there are no pending buffers after the caller sends a <b>REQUEST_ISOCH_STOP</b> request and before the caller sends a <b>REQUEST_ISOCH_MODIFY_STREAM_PROPERTIES</b> request.  </p>