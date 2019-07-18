---
UID: NS:1394._IRB_REQ_ASYNC_STREAM
title: _IRB_REQ_ASYNC_STREAM (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to carry out an asynchronous write request.
old-location: ieee\irb_req_async_stream.htm
tech.root: IEEE
ms.assetid: 9E4958B0-066F-4485-AFF2-3AE499AF3E64
ms.date: 02/15/2018
ms.keywords: 1394/IRB_REQ_ASYNC_STREAM, IEEE.irb_req_async_stream, IRB_REQ_ASYNC_STREAM, IRB_REQ_ASYNC_STREAM structure [Buses], _IRB_REQ_ASYNC_STREAM
ms.topic: struct
f1_keywords:
 - "1394/IRB_REQ_ASYNC_STREAM"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 1394.h
api_name:
- IRB_REQ_ASYNC_STREAM
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_ASYNC_STREAM
---

# _IRB_REQ_ASYNC_STREAM structure


## -description


This structure contains the fields necessary for the 1394 bus driver to carry out an asynchronous write request.


## -struct-fields




### -field nNumberOfBytesToStream

Specifies the number of bytes to write.


### -field fulFlags

Reserved. Drivers must set this to zero.


### -field Mdl

Specifies the source buffer.


### -field ulTag

Specifies the Tag field for any packets generated from this request.


### -field nChannel

Specifies the channel to which the data will be written.


### -field ulSynch

Specifies the Sy field for any packets generated from this request.


### -field Reserved

Reserved. Drivers must set this to zero.


### -field nSpeed

Specifies the transfer rate. The possible speed values are SPEED_FLAGS_xxx, where xxx is the (approximate) transfer rate in megabits per second. Existing hardware currently supports transfer rates of 100, 200, and 400 Mb/sec.

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
 

<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">New Flags for Speed and Payload Size</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>
