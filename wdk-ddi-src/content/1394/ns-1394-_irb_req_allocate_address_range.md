---
UID: NS:1394._IRB_REQ_ALLOCATE_ADDRESS_RANGE
title: _IRB_REQ_ALLOCATE_ADDRESS_RANGE (1394.h)
description: This structure contains the fields necessary for the 1394 stack to carry out a request to allocate an address range.
old-location: ieee\irb_req_allocate_address_range.htm
tech.root: IEEE
ms.assetid: 76D306DF-D604-4B3C-BFED-A855113A55A9
ms.date: 02/15/2018
keywords: ["_IRB_REQ_ALLOCATE_ADDRESS_RANGE structure"]
ms.keywords: 1394/IRB_REQ_ALLOCATE_ADDRESS_RANGE, IEEE.irb_req_allocate_address_range, IRB_REQ_ALLOCATE_ADDRESS_RANGE, IRB_REQ_ALLOCATE_ADDRESS_RANGE structure [Buses], _IRB_REQ_ALLOCATE_ADDRESS_RANGE
f1_keywords:
 - "1394/IRB_REQ_ALLOCATE_ADDRESS_RANGE"
 - "IRB_REQ_ALLOCATE_ADDRESS_RANGE"
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
- IRB_REQ_ALLOCATE_ADDRESS_RANGE
targetos: Windows
req.typenames: IRB_REQ_ALLOCATE_ADDRESS_RANGE
---

# _IRB_REQ_ALLOCATE_ADDRESS_RANGE structure


## -description


This structure contains the fields necessary for the 1394 stack to carry out a request to allocate an address range.

If the allocation is specified with no notification options and no <b>RequiredOffset</b>, the returned address will always be a physical address on the OHCI bus. As a result, during allocation, if <b>Callback</b> and <b>Context</b> are specified, because no notification is used, the callback will be used to notify the caller that the allocation is complete. This way, the issuer of the alloc does not have to block, but instead, the issuer's callback routine is called asynchronously when this is complete.

The caller must create this IRB as usual, but instead use the physical mapping routine provided by the port driver in order to use this request. If it uses <b>IoCallDriver</b>, the caller cannot specify <b>Context</b> and <b>Callback</b> for a physical address, and it has to block.


## -struct-fields




### -field Mdl

If non-<b>NULL</b>, points to the MDL that describes the application's buffer where asynchronous operations are to be read, written, or locked. The memory for the MDL must be allocated from nonpaged pool or locked down by means of a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>. If the driver specifies <b>u.AllocateAddressRange.Mdl</b>, then <b>u.AllocateAddressRange.FifoSListHead</b> and <b>u.AllocateAddressRange.FifoSpinLock</b> must be <b>NULL</b>.


### -field fulFlags

Specifies whether the array entries in p1394AddressRange use big-endian byte order. If the caller specifies BIG_ENDIAN_ADDRESS_RANGE, the array entries are in big-endian byte order (the native byte order of the IEEE 1394 protocol), even if the local host is a little-endian machine. In order to specify a little-endian address range, the caller must explicitly guarantee that the BIG_ENDIAN_ADDRESS_RANGE flag is not set using a statement similar to the following:

fulFlags = fulFlags & ~(0x0ffffffff & BIG_ENDIAN_ADDRESS_RANGE)


### -field nLength

Specifies the number of the IEEE 1394 addresses to allocate.


### -field MaxSegmentSize

Specifies the maximum size for each range of addresses that the bus driver allocates. Use zero to indicate that the driver does not have a required maximum segment size. If a nonzero value is specified for <b>MaxSegmentSize</b>, the value must be less than 64 KB (65,536 bytes). In other words, it must be less than or equal to 65,535 (0xFFFF) due to the fact that the address range size is stored in a 16-bit word. This member is ignored if <b>u.AllocateAddressRange.Required1394Offset</b> is non-<b>NULL</b>.


### -field fulAccessType

Specifies access type using one or more of the following flags.

<table>
<tr>
<th>Access</th>
<th>Description</th>
</tr>
<tr>
<td>
ACCESS_FLAGS_TYPE_READ 

</td>
<td>
Allocated addresses can be read.

</td>
</tr>
<tr>
<td>
ACCESS_FLAGS_TYPE_WRITE 

</td>
<td>
Allocated addresses can be written to.

</td>
</tr>
<tr>
<td>
ACCESS_FLAGS_TYPE_LOCK 

</td>
<td>
Allocated addresses can be the target of a lock operation.

</td>
</tr>
<tr>
<td>
 ACCESS_FLAGS_TYPE_BROADCAST

</td>
<td>
Allocated addresses can receive asynchronous I/O requests from any node on the bus. (By default, only the device driver's device can send requests to the allocated addresses).

</td>
</tr>
</table>
 

Special considerations apply to drivers of virtual devices. Virtual devices do not have node IDs, and so when a driver sends a request to a virtual device, the bus driver has no means of identifying which device is the target. Thus in order for a virtual device to receive requests, its driver must allocate a range of addresses with the ACCESS_FLAGS_TYPE_BROADCAST flag set in <b>fulAccessType</b>. This permits the virtual device to receive all request packets, no matter what node ID is indicated in the request packet. 


### -field fulNotificationOptions

If the device driver requests that the bus driver handle each request, and notifies the device driver upon completion, this specifies which asynchronous I/O request types will trigger the bus driver to the notify the device driver upon completion. See the <b>Operation</b> section for more details. The driver may specify one or more of the NOTIFY_FLAGS_AFTER_XXX flags.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
 NOTIFY_FLAGS_NEVER

</td>
<td>
No notification.

</td>
</tr>
<tr>
<td>
NOTIFY_FLAGS_AFTER_READ 

</td>
<td>
Notify the device driver after carrying out an asynchronous read operation.

</td>
</tr>
<tr>
<td>
NOTIFY_FLAGS_AFTER_WRITE 

</td>
<td>
Notify the device driver after carrying out an asynchronous write operation.

</td>
</tr>
<tr>
<td>
NOTIFY_FLAGS_AFTER_LOCK 

</td>
<td>
Notify the device driver after carrying out an asynchronous lock operation.

</td>
</tr>
</table>
 


### -field Callback

Points to a device driver callback routine. If the device driver specifies that the bus driver notify the device driver for each asynchronous I/O request, <b>u.AllocateAddressRange.Callback</b> points to the device driver's notification routine, which must have the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID DriverNotificationRoutine(IN PNOTIFICATION_INFO );</pre>
</td>
</tr>
</table></span></div>
If the device driver specifies that it receives no notification, and submits this request at raised IRQL through the port driver's physical mapping routine, then <b>u.AllocateAddressRange.Callback</b> points to the device driver's allocation completion routine, which must have the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID AllocationCompletionRoutine( IN PVOID );</pre>
</td>
</tr>
</table></span></div>
Drivers that do not request notification, and submit this request in the normal way at PASSIVE_LEVEL, must set this member to <b>NULL</b>.


### -field Context

Points to any context data that the device driver wants to pass for this set of addresses. If the provided callback (see previous) is a notification routine, the bus driver passes <b>u.AllocateAddressRange.Context</b> within the NOTIFICATION_INFO the parameter. If the callback is an allocation completion routine, the bus driver passes <b>u.AllocateAddressRange.Context</b> as the sole parameter to the routine


### -field Required1394Offset

Specifies a hard-coded address in the computer's IEEE 1394 address space. The bus driver allocates the addresses beginning at <b>u.AllocateAddressRange.Required1394Offset</b>. If no specific address is required, the driver should fill in each member of the ADDRESS_OFFSET with zero. The bus driver then chooses the addresses to allocate.


### -field FifoSListHead

If non-<b>NULL</b>, specifies a properly initialized (for example, by <b>ExInitializeSListHead</b>) interlocked, singly-linked list of ADDRESS_FIFO elements. Each ADDRESS_FIFO contains an MDL. As the bus driver handles each incoming write request to the allocated addresses, it pops off the first element on the list and writes incoming data to the MDL. It then calls the driver's notification routine.

Each MDL provided must only span one page in memory. The driver can add or remove elements from the ADDRESS_FIFO list by using <b>ExInterlockedPushEntrySList</b> and <b>ExInterlockedPopEntrySList</b>.

If this member is non-<b>NULL</b>, the <b>Mdl</b> member of <b>u.AllocateAddress</b> range must be <b>NULL</b>, the <b>fulNotificationOptions</b> member must be NOTIFY_FLAGS_AFTER_WRITE (no other flags must be specified), and the driver must provide a spin lock in <b>FifoSpinLock</b>. This implies that the order in which packets are filled and returned is guaranteed to be based on a FIFO algorithm.  In fact, this SLIST-based mechanism acts more like a stack, or Last-In-First-Out (LIFO).


### -field FifoSpinLock

If non-<b>NULL</b>, specifies a properly initialized spin lock (for example, by <b>KeInitializeSpinLock</b>). The spin lock is used to serialize access to the SList provided in <b>u.AllocateAddressRange.FifoSListHead</b>.

The <b>u.AllocateAddressRange.FifoSpinLock</b> member is non-<b>NULL</b> if and only if <b>u.AllocateAddressRange.FifoSListHead</b> is non-<b>NULL</b> as well.


### -field AddressesReturned

Number of addresses returned.


### -field p1394AddressRange

Points to an array of ADDRESS_RANGE structures. The array must be large enough to hold the maximum number of structures the bus driver can return.

If the driver specifies a required address offset, or if the driver does not provide any backing store, the bus driver only returns one address range. If the driver provides backing store in <b>u.AllocateAddressRange.Mdl</b> the bus driver segments the allocated addresses along physical memory boundaries. If the <b>MaxSegmentSize</b> of <b>u.AllocateAddressRange</b> is 0, or if <b>MaxSegmentSize</b> is bigger than the page size, the driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">ADDRESS_AND_SIZE_TO_SPAN_PAGES</a> macro to determine the worst case. Otherwise, the maximum number of addresses ranges returned by the bus driver is <b>u.AllocateAddressRange.nLength</b> / <b>u.MaxSegmentSize</b>. If a nonzero value is specified for <b>MaxSegmentSize</b>, the value must be less than 64 KB (65,536 bytes). In other words, it must be less than or equal to 65,535 (0xFFFF) due to the fact that the address range size is stored in a 16-bit word.


### -field hAddressRange

Handle to the address range.


### -field DeviceExtension

Points to the device extension associated with the device object. Not setting this member can lead to unexpected behavior when the driver tries to access the allocated address space.

