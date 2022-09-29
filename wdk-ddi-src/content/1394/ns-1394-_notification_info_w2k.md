---
UID: NS:1394._NOTIFICATION_INFO_W2K
title: _NOTIFICATION_INFO_W2K (1394.h)
description: The bus driver passes NOTIFICATION_INFO_W2K to the driver-provided notification routine for a driver-allocated address range in an IEEE 1394 address space.
old-location: ieee\notification_info.htm
tech.root: IEEE
ms.date: 07/22/2022
keywords: ["NOTIFICATION_INFO_W2K structure"]
ms.keywords: "*PNOTIFICATION_INFO, *PNOTIFICATION_INFO_W2K, 1394/NOTIFICATION_INFO, 1394/PNOTIFICATION_INFO, 1394stct_db1356d4-c42d-46a4-bbc4-ed8452dc2212.xml, IEEE.notification_info, NOTIFICATION_INFO, NOTIFICATION_INFO structure [Buses], NOTIFICATION_INFO_W2K, NOTIFICATION_INFO_WXP, PNOTIFICATION_INFO, PNOTIFICATION_INFO structure pointer [Buses], _NOTIFICATION_INFO_W2K"
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
req.typenames: NOTIFICATION_INFO_W2K, *PNOTIFICATION_INFO_W2K
f1_keywords:
 - _NOTIFICATION_INFO_W2K
 - 1394/_NOTIFICATION_INFO_W2K
 - PNOTIFICATION_INFO_W2K
 - 1394/PNOTIFICATION_INFO_W2K
 - NOTIFICATION_INFO_W2K
 - 1394/NOTIFICATION_INFO_W2K
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _NOTIFICATION_INFO_W2K
 - PNOTIFICATION_INFO_W2K
 - NOTIFICATION_INFO_W2K
---

# _NOTIFICATION_INFO_W2K structure

## -description

The bus driver passes NOTIFICATION_INFO to pass information to the driver-provided notification routine for a driver-allocated address range in the computer's IEEE 1394 address space. The bus driver calls the notification routine when it receives an asynchronous I/O request packet for that address.

## -struct-fields

### -field Mdl

If non-**NULL**, **Mdl** specifies the [memory descriptor list (MDL)](/windows-hardware/drivers/) for the allocated address range.

### -field ulOffset

Specifies the byte offset with the MDL that corresponds to the address that received a request packet. Only used when **Mdl** is non-**NULL**.

### -field nLength

Specifies the number of bytes affected by the request packet. Only used when **Mdl** is non-**NULL**.

### -field fulNotificationOptions

Specifies which type of event triggered the bus driver to call the notification routine. The possible events the bus driver can return are the following:

- NOTIFY_FLAGS_AFTER_READ
- NOTIFY_FLAGS_AFTER_WRITE
- NOTIFY_FLAGS_AFTER_LOCK

This member is only used when **Mdl** is non-**NULL**.

### -field Context

Pointer to specific context data for this allocated address range. The driver supplies this data through the **u.AllocateAddressRange.Context** member of the IRB for the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field Fifo

Pointer to the [ADDRESS_FIFO](/windows-hardware/drivers/ddi/1394/ns-1394-_address_fifo) structure that contains the FIFO element just completed. Only used if the driver submitted an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field RequestPacket

If non-**NULL**, **RequestPacket** points to the original request packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponseMdl

If non-**NULL**, **ResponseMdl** points to an uninitialized MDL. The driver must initialize this MDL for a nonpageable buffer, and fill the buffer with the response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponsePacket

If non-**NULL**, **ResponsePacket** points to a memory location that the driver fills in with a pointer to the data (quadlet or block) to be returned in the response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponseLength

If non-**NULL**, **ResponseLength** points to a memory location that the driver fills in with the length of its response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

### -field ResponseEvent

If non-**NULL**, **ResponseEvent** points to a memory location that the driver fills in with the kernel event the bus driver should use to signal that it has completed sending the response packet. The bus driver only supplies this if the device driver did not supply an MDL or an ADDRESS_FIFO list in the original REQUEST_ALLOCATE_ADDRESS_RANGE request.

## -remarks

When a driver allocates an address range on the computer's IEEE 1394 address space, it may require that the bus driver notify it for some or all request packets sent to the allocated addresses. As part of the original allocate request, the driver may either require that the bus driver forward each packet for handling, or it may require that the bus driver handle the packet and notify the device driver when it has finished. For more information, see [REQUEST_ALLOCATE_ADDRESS_RANGE](/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class).

If the device driver provides no backing store, the bus driver forwards each packet to the device driver for handling. The bus driver passes **NULL** for **Mdl**, and passes the packet in **RequestPacket**. The bus driver also passes pointers to memory locations that the device driver must fill in with the buffer for the response packet (in **ResponsePacket**), the buffer length (in **ResponseLength**), and an MDL for the buffer (in **ResponseMdl**). The bus driver also supplies a memory location that the driver can use to pass a kernel event object in **ResponseEvent**. If the device driver provides an event object, the bus driver uses it to signal the driver when it has finished sending the response packet.

If the driver provides the backing store in the original allocate address range request, the bus driver uses the driver's notification routine to signal that it has completed reading or writing data from the backing store. It passes the MDL of the backing store in the **Mdl** member, and the starting location and size within the associated buffer in **ulOffset** and **nLength**. The bus driver also passes the type of event that led to notification in **fulNotificationOptions**.

If the device driver is using a linked list of ADDRESS_FIFO's as the backing store, the bus driver returns the list element it popped off in **Fifo**.

## -see-also

[REQUEST_ALLOCATE_ADDRESS_RANGE](/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class)
