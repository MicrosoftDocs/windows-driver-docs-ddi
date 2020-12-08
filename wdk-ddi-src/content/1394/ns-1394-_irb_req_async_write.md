---
UID: NS:1394._IRB_REQ_ASYNC_WRITE
title: _IRB_REQ_ASYNC_WRITE (1394.h)
description: This structure contains the fields necessary for the 1394 stack to carry out an asynchronous write request.
old-location: ieee\irb_req_async_write.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IRB_REQ_ASYNC_WRITE structure"]
ms.keywords: 1394/IRB_REQ_ASYNC_WRITE, IEEE.irb_req_async_write, IRB_REQ_ASYNC_WRITE, IRB_REQ_ASYNC_WRITE structure [Buses], _IRB_REQ_ASYNC_WRITE
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
req.typenames: IRB_REQ_ASYNC_WRITE
f1_keywords:
 - _IRB_REQ_ASYNC_WRITE
 - 1394/_IRB_REQ_ASYNC_WRITE
 - IRB_REQ_ASYNC_WRITE
 - 1394/IRB_REQ_ASYNC_WRITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_ASYNC_WRITE
---

# _IRB_REQ_ASYNC_WRITE structure


## -description

This structure contains the fields necessary for the 1394 stack to carry out an asynchronous write request.

## -struct-fields

### -field DestinationAddress

Specifies the 1394 64-bit destination address for this write operation. The driver only must fill in the <b>IA_Destination_Offset</b> member of <b>u.AsyncWrite.DestinationAddress</b>; the bus driver fills in the <b>IA_Destination_ID</b> member. See <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_io_address">IO_ADDRESS</a> for the structure description.

### -field nNumberOfBytesToWrite

Specifies the number of bytes to write to the 1394 node.

### -field nBlockSize

Specifies the size of each individual block within the data stream that is written as a whole to the node. If this parameter is zero, then the maximum packet size for the speed selected is used in breaking up these write requests, unless raw-mode addressing is used.



If raw-mode addressing is used, the client driver should set the <b>nBlockSize</b> member to the maximum asynchronous payload size that is supported by the device at the connected speed. 

For more information on raw-mode addressing, see <a href="/windows-hardware/drivers/ieee/sending-asynchronous-i-o-request-packets-on-the-ieee-1394-bus">Sending Asynchronous I/O Request Packets on the IEEE 1394 Bus.</a>


<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">New Flags for Speed and Payload Size</a> and <a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>

### -field fulFlags

Specifies any nondefault settings for this operation. The following flags are provided.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
 ASYNC_FLAGS_NONINCREMENTING

</td>
<td>
Do not increment 1394 address during asynchronous operation. This flag is set only in large asynchronous requests (that is, those greater than asynchronous packet size).

</td>
</tr>
<tr>
<td>
ASYNC_FLAGS_NO_STATUS

</td>
<td>
Always return success from the write operation, whether the write succeeds or fails.

</td>
</tr>
<tr>
<td>
ASYNC_FLAGS_BROADCAST

</td>
<td>
Broadcast to all nodes on the bus.

</td>
</tr>
</table>
 

Use the bitwise operator OR to combine the settings.

### -field Mdl

Points to an MDL that describes the device driver's buffer, which receives data from the 1394 node.

### -field ulGeneration

Specifies the bus reset generation as known by the device driver that submitted this asynchronous request. If the generation count specified does not match the actual generation of the bus, this request is returned with a status of STATUS_INVALID_GENERATION.

### -field chPriority

Reserved.

### -field nSpeed

Reserved.

### -field tCode

Reserved.

### -field Reserved

Reserved.

### -field ElapsedTime

Elapsed time in nanoseconds. Only valid for flag <b>ASYNC_FLAGS_PING</b>.
