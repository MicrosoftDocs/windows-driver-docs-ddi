---
UID: NS:1394._IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
title: _IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH (1394.h)
description: This structure contains the fields necessary in order for the Bus driver to carry out an IsochAllocateBandwidth request.
old-location: ieee\irb_req_isoch_allocate_bandwidth.htm
tech.root: IEEE
ms.assetid: 68118E69-5644-4FE4-A75B-CE0FC427BA06
ms.date: 02/15/2018
keywords: ["IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH, IEEE.irb_req_isoch_allocate_bandwidth, IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH, IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH structure [Buses], _IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
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
req.typenames: IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
f1_keywords:
 - _IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
 - 1394/_IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
 - IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
 - 1394/IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH
---

# _IRB_REQ_ISOCH_ALLOCATE_BANDWIDTH structure


## -description

This structure contains the fields necessary in order for the Bus driver to carry out an <b>IsochAllocateBandwidth</b> request.

## -struct-fields

### -field nMaxBytesPerFrameRequested

Specifies the bandwidth requested, in bytes per isochronous frame. If the host controller is configured to strip away the packet headers, the device driver does not need to include the packet header size in the number of bytes requested. The driver also does not need to round the value up to the nearest quadlet.

### -field fulSpeed

Specifies the connection speed to use in allocating bandwidth. The possible speed values are SPEED_FLAGS_xxx, where xxx is the (approximate) transfer rate in megabits per second. Existing hardware supports transfer rates of 100, 200, and 400 Mb/sec.

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

### -field hBandwidth

Specifies the handle to use to refer to the bandwidth resource. The caller can set the IRB_FLAG_ALLOW_REMOTE_FREE flag in <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_irb">IRB</a> structure to indicate that the system should free the memory allocated for this handle. If caller does not set this flag, then caller will have to free the bandwidth handle.

### -field BytesPerFrameAvailable

Specifies the bytes per frame that are available after the allocation attempt. Drivers should not rely on this bandwidth being available, since another device may allocate or deallocate bandwidth at any time. The bus driver fills in this member, even if the request fails.

### -field SpeedSelected

Specifies the actual speed selected in allocating bandwidth. The value is one of SPEED_FLAGS_xxx (see the <b>fulSpeed</b> member description above).

<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">New Flags for Speed and Payload Size</a> and <a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>

### -field nBandwidthUnitsRequired

This is a pre-calculated value.