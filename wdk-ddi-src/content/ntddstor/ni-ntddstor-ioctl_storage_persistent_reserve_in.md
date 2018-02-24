---
UID: NI:ntddstor.IOCTL_STORAGE_PERSISTENT_RESERVE_IN
title: IOCTL_STORAGE_PERSISTENT_RESERVE_IN
author: windows-driver-content
description: The generic storage class driver (classpnp.sys) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve In commands.
old-location: storage\ioctl_storage_persistent_reserve_in.htm
old-project: storage
ms.assetid: a5a3e98b-8f6b-412d-a2eb-a28b5664340d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_storage_persistent_reserve_in, IOCTL_STORAGE_PERSISTENT_RESERVE_IN control code [Storage Devices], IOCTL_STORAGE_PERSISTENT_RESERVE_IN, ntddstor/IOCTL_STORAGE_PERSISTENT_RESERVE_IN, k307_d142d4f6-d2a1-420e-a41d-5bb630445ad2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_PERSISTENT_RESERVE_IN
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_PERSISTENT_RESERVE_IN IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The generic storage class driver (<i>classpnp.sys</i>) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve In commands. The behavior of the storage device when a Persistent Reserve In command is received is described in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification. The IOCTL interface requires the caller to have read access to the physical device for Persistent Reserve In commands. User-mode applications, services, and kernel-mode drivers can use this IOCTL to control persistent reservations. If called from a driver, this IOCTL must be called from a thread running at IRQL &lt; DISPATCH_LEVEL. This IOCTL is defined with FILE_READ_ACCESS, requiring a device handle to have read permissions to issue the Persistent Reserve In command.


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddstor\ns-ntddstor-_persistent_reserve_command.md">PERSISTENT_RESERVE_COMMAND</a> structure. You must allocate the buffer from nonpaged pool and must align it correctly for the  target device and adapter.

PR_IN.ServiceAction can be one of the following:

<ul>
<li>
RESERVATION_ACTION_READ_KEYS

</li>
<li>
RESERVATION_ACTION_READ_RESERVATIONS

</li>
</ul>
PR_IN.Allocation length is the size (in bytes) of the buffer allocated for the returned parameter list.


### -input-buffer-length

The length of .


### -output-buffer

For PR_IN.ServiceAction = RESERVATION_ACTION_READ_KEYS, the output buffer contains a <a href="..\storport\ns-storport-pri_registration_list.md">PRI_REGISTRATION_LIST</a> structure and must be at least sizeof(PRI_REGISTRATION_LIST).

For PR_IN.ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS, the output buffer contains a <a href="..\storport\ns-storport-pri_reservation_list.md">PRI_RESERVATION_LIST</a> structure and must be at least sizeof(PRI_RESERVATION_LIST).

If the allocated buffer is too small to return all the Persistent Reserve In data, success will be returned and the required size will be returned in the parameter list <b>AdditionalLength</b> field.


### -output-buffer-length

The length of .


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the size of the output buffer. For ServiceAction = RESERVATION_ACTION_READ_KEYS, the output buffer is a <a href="..\storport\ns-storport-pri_registration_list.md">PRI_REGISTRATION_LIST</a> structure. For ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS, the output buffer is a <a href="..\storport\ns-storport-pri_reservation_list.md">PRI_RESERVATION_LIST</a> structure.

The <b>Status</b> field is set to one of the following:




#### -STATUS_BUFFER_OVERFLOW (ERROR_MORE_DATA)

The output buffer is too small to hold the Persistent Reserve In data. The output buffer's <b>AdditionalLength</b> field will contain the size of the data to be returned.


#### -STATUS_DEVICE_BUSY (ERROR_BUSY)

The command failed because of a Reservation Conflict (for more information, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification).


#### -STATUS_INFO_LENGTH_MISMATCH

The input buffer length for the IOCTL is less than sizeof(PERSISTENT_RESERVE_COMMAND) or the size that is specified in the <a href="..\ntddstor\ns-ntddstor-_persistent_reserve_command.md">PERSISTENT_RESERVE_COMMAND</a> data structure is less than sizeof(PERSISTENT_RESERVE_COMMAND).


#### -STATUS_INVALID_DEVICE_REQUEST (ERROR_INVALID_FUNCTION)

The I/O control code (IOCTL_STORAGE_PERSISTENT_RESERVE_IN) is not supported by the storage drivers.


#### -STATUS_INVALID_PARAMETER (ERROR_INVALID_PARAMETER)

The input buffer structure is incorrectly sized or populated.


#### -STATUS_INVALID_USER_BUFFER (ERROR_INVALID_USER_BUFFER)

The input or output buffer is not aligned correctly for the device or adapter.  This status could only be returned when a driver sends an IOCTL to the storage stack.  This status will not be returned when a user-mode application sends the IOCTL through the DeviceIoControl API as the I/O Manager automatically aligns the buffers.


#### -STATUS_IO_DEVICE_ERROR (ERROR_IO_DEVICE)

The device does not support the Persistent Reserve In command.


#### -STATUS_SUCCESS

The operation was successful.

