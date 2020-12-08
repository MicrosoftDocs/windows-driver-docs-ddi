---
UID: NS:1394._IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
title: _IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to carry out a IsochAllocateResources request.
old-location: ieee\irb_req_isoch_allocate_resources_wxp.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP, 1394/PIRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP, IEEE.irb_req_isoch_allocate_resources_wxp, IRB_REQ_ISOCH_ALLOCATE_RESOURCES, IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP, IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP structure [Buses], PIRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP, PIRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP structure pointer [Buses], _IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
req.header: 1394.h
req.include-header: 
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
targetos: Windows
req.typenames: IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
f1_keywords:
 - _IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
 - 1394/_IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
 - IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
 - 1394/IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP
---

# _IRB_REQ_ISOCH_ALLOCATE_RESOURCES_WXP structure


## -description

This structure contains the fields necessary for the 1394 bus driver to carry out a IsochAllocateResources request.

## -struct-fields

### -field fulSpeed

Specifies the connection speed to use for communication on the channel. The possible speed values are SPEED_FLAGS_xxx, where xxx is the (approximate) transfer rate in megabits per second. Existing hardware supports transfer rates of 100, 200, and 400 Mb/sec.

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
 

<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">New Flags for Speed and Payload Size</a> and <a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>

### -field fulFlags

Specifies how the bus driver should use any buffers attached to the resource handle. Many of the flags specify how the bus driver should configure the IEEE host controller for DMA from or to attached buffers.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
 RESOURCE_USED_IN_LISTENING 

</td>
<td>
Attached buffers are used to read data from an  isochronous channel. Set this if the resource handle will be used in a REQUEST_ISOCH_LISTEN request.

</td>
</tr>
<tr>
<td>
RESOURCE_USED_IN_TALKING 

</td>
<td>
Attached buffers are used to write data to an isochronous channel. Set this if the resource handle will be used in a REQUEST_ISOCH_TALK request.

</td>
</tr>
<tr>
<td>
RESOURCE_STRIP_ADDITIONAL_QUADLETS 

</td>
<td>
The bus driver configures the host controller to strip  additional quadlets from incoming isochronous packets. The number of quadlets to be stripped is specified in <b>nQuadletsToStrip</b>.

</td>
</tr>
<tr>
<td>
RESOURCE_SYNCH_ON_TIME

</td>
<td>
The bus driver configures the host controller to synchronize the beginning of the isochronous transaction to the CYCLE_TIME specified in the StartTime member of the request's IRB. See REQUEST_ISOCH_LISTEN or REQUEST_ISOCH_TALK.

</td>
</tr>
<tr>
<td>
RESOURCE_USE_PACKET_BASED

</td>
<td>
Used to switch to packet-based transfer, rather than the default. The default is stream-based transfer, unless the host controller only supports packet-based DMA.

</td>
</tr>
<tr>
<td>
RESOURCE_USE_MULTICHANNEL

</td>
<td>
The driver owning this resource listens on multiple channels. 

</td>
</tr>
<tr>
<td>
RESOURCE_VARIABLE_ISOCH_PAYLOAD

</td>
<td>
The driver owning this resource transfers frames of variable size. 

</td>
</tr>
</table>

### -field nChannel

Specifies the isochronous channel for all transactions involving the resource handle allocated by this request.

### -field nMaxBytesPerFrame

Specifies the expected maximum isochronous frame size while transmitting and receiving on the channel.

### -field nNumberOfBuffers

Specifies one more than the maximum expected number of buffers that are attached to the resource handle at any given time.

### -field nMaxBufferSize

Specifies the maximum size of the buffers that are attached to the resource handle.

### -field nQuadletsToStrip

Specifies the number of quadlets to strip from the beginning of every packet in an incoming isochronous stream. This parameter is ignored unless the device driver sets the  RESOURCE_STRIP_ADDITIONAL_QUADLETS flag in <b>u.IsochAllocateResources.fulFlags</b>.

### -field hResource

Specifies a handle to the resource.

### -field ChannelMask

Specifies a set of isochronous channels, if RESOURCE_USE_MULTICHANNEL is set, that are used for all transactions involving the resource handle allocated by this request.
