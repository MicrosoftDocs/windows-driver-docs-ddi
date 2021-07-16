---
UID: NS:1394._NOTIFICATION_INFO_WXP
title: _NOTIFICATION_INFO_WXP (1394.h)
description: The bus driver passes NOTIFICATION_INFO_WXP to pass information to the driver-provided notification routine for a driver-allocated address range in the computer's IEEE 1394 address space.
old-location: ieee\notification_info.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["NOTIFICATION_INFO_WXP structure"]
ms.keywords: "*PNOTIFICATION_INFO, *PNOTIFICATION_INFO_WXP, 1394/NOTIFICATION_INFO, 1394/PNOTIFICATION_INFO, 1394stct_db1356d4-c42d-46a4-bbc4-ed8452dc2212.xml, IEEE.notification_info, NOTIFICATION_INFO, NOTIFICATION_INFO structure [Buses], NOTIFICATION_INFO_W2K, NOTIFICATION_INFO_WXP, PNOTIFICATION_INFO, PNOTIFICATION_INFO structure pointer [Buses], _NOTIFICATION_INFO_WXP"
req.header: 1394.h
req.include-header: 1394.h
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
req.typenames: NOTIFICATION_INFO_WXP, *PNOTIFICATION_INFO_WXP
f1_keywords:
 - _NOTIFICATION_INFO_WXP
 - 1394/_NOTIFICATION_INFO_WXP
 - PNOTIFICATION_INFO_WXP
 - 1394/PNOTIFICATION_INFO_WXP
 - NOTIFICATION_INFO_WXP
 - 1394/NOTIFICATION_INFO_WXP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _NOTIFICATION_INFO_WXP
 - PNOTIFICATION_INFO_WXP
 - NOTIFICATION_INFO_WXP
---

# _NOTIFICATION_INFO_WXP structure


## -description

The bus driver passes NOTIFICATION_INFO to pass information to the driver-provided notification routine for a driver-allocated address range in the computer's IEEE 1394 address space. The bus driver calls the notification routine when it receives an asynchronous I/O request packet for that address.

## -struct-fields

### -field Mdl

If non-<b>NULL</b>, <b>Mdl</b> specifies the <a href="/windows-hardware/drivers/">memory descriptor list (MDL)</a>  for the allocated address range.

### -field ulOffset

Specifies the byte offset with the MDL that corresponds to the address that received a request packet. Only used when <b>Mdl</b> is non-<b>NULL</b>.

### -field nLength

Specifies the number of bytes affected by the request packet. Only used when <b>Mdl</b> is non-<b>NULL</b>.

### -field fulNotificationOptions

Specifies which type of event triggered the bus driver to call the notification routine. The possible events the bus driver can return are the following:

<ul>
<li> NOTIFY_FLAGS_AFTER_READ</li>
<li> NOTIFY_FLAGS_AFTER_WRITE</li>
<li> NOTIFY_FLAGS_AFTER_LOCK</li>
</ul>
This member is only used when <b>Mdl</b> is non-<b>NULL</b>.

### -field Context

Pointer to specific context data for this allocated address range. The driver supplies this data through the <b>u.AllocateAddressRange.Context</b> member of the IRB for the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field Fifo

Pointer to the <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_address_fifo">ADDRESS_FIFO</a> structure that contains the FIFO element just completed. Only used if the driver submitted an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field RequestPacket

If non-<b>NULL</b>, <b>RequestPacket</b> points to the original request packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponseMdl

If non-<b>NULL</b>, <b>ResponseMdl</b> points to an uninitialized MDL. The driver must initialize this MDL for a nonpageable buffer, and fill the buffer with the response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponsePacket

If non-<b>NULL</b>, <b>ResponsePacket</b> points to a memory location that the driver fills in with a pointer to the data (quadlet or block) to be returned in the response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponseLength

If non-<b>NULL</b>, <b>ResponseLength</b> points to a memory location that the driver fills in with the length of its response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponseEvent

If non-<b>NULL</b>, <b>ResponseEvent</b> points to a memory location that the driver fills in with the kernel event the bus driver should use to signal that it has completed sending the response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.


#### - ResponseCode

Specifies the result of the driver's response to the request. The driver must report the response result by setting <b>ResponseCode</b> to a valid RCODE value.

The following table describes the RCODE values:

<table>
<tr>
<th>RCODE value</th>
<th>Description</th>
</tr>
<tr>
<td>RCODE_RESPONSE_COMPLETE</td>
<td>The driver has successfully completed the request.</td>
</tr>
<tr>
<td>RCODE_RESERVED1</td>
<td>Reserved. The driver must not use this value to report the response result.</td>
</tr>
<tr>
<td>RCODE_RESERVED2</td>
<td>Reserved. The driver must not use this value to report the response result.</td>
</tr>
<tr>
<td>RCODE_RESERVED3</td>
<td>Reserved. The driver must not use this value to report the response result.</td>
</tr>
<tr>
<td>RCODE_CONFLICT_ERROR</td>
<td>A resource conflict was detected. The request may be retried by the bus driver.</td>
</tr>
<tr>
<td>RCODE_DATA_ERROR</td>
<td>A hardware error has occurred and data is unavailable.</td>
</tr>
<tr>
<td>RCODE_TYPE_ERROR</td>
<td>A member in the request packet header was set to an unsupported or incorrect
value, or an invalid transaction was attempted (such as  a write request to a read-only
address).
</td>
</tr>
<tr>
<td>RCODE_ADDRESS_ERROR</td>
<td>The destination offset member in the request packet was set to an invalid or inaccessible address.
</td>
</tr>
<tr>
<td>RCODE_TIMED_OUT</td>
<td>The 1394 device did not respond to the request.</td>
</tr>
</table>
 

<div class="alert"><b>Important</b>  Under certain conditions in Windows 7, a memory leak could occur if the driver's notification routine modifies the <b>ResponseCode</b> member.</div>
<div> </div>

## -remarks

When a driver allocates an address range on the computer's IEEE 1394 address space, it may require that the bus driver notify it for some or all request packets sent to the allocated addresses. As part of the original allocate request, the driver may either require that the bus driver forward each packet for handling, or it may require that the bus driver handle the packet and notify the device driver when it has finished. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>. 

If the device driver provides no backing store, the bus driver forwards each packet to the device driver for handling. The bus driver passes <b>NULL</b> for <b>Mdl</b>, and passes the packet in <b>RequestPacket</b>. The bus driver also passes pointers to memory locations that the device driver must fill in with the buffer for the response packet (in <b>ResponsePacket</b>), the buffer length (in <b>ResponseLength</b>), and an MDL for the buffer (in <b>ResponseMdl</b>). The bus driver also supplies a memory location that the driver can use to pass a kernel event object in <b>ResponseEvent</b>. If the device driver provides an event object, the bus driver uses it to signal the driver when it has finished sending the response packet.

If the driver provides the backing store in the original allocate address range request, the bus driver uses the driver's notification routine to signal that it has completed reading or writing data from the backing store. It passes the MDL of the backing store in the <b>Mdl</b> member, and the starting location and size within the associated buffer in <b>ulOffset</b> and <b>nLength</b>. The bus driver also passes the type of event that led to notification in <b>fulNotificationOptions</b>.

If the device driver is using a linked list of ADDRESS_FIFO's as the backing store, the bus driver returns the list element it popped off in <b>Fifo</b>.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>

