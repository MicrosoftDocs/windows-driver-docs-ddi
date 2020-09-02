---
UID: NI:ntddstor.IOCTL_STORAGE_PERSISTENT_RESERVE_OUT
title: IOCTL_STORAGE_PERSISTENT_RESERVE_OUT (ntddstor.h)
description: The generic storage class driver (classpnp.sys) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve Out commands.
old-location: storage\ioctl_storage_persistent_reserve_out.htm
tech.root: storage
ms.assetid: a9863ac9-46e2-4888-879e-7d56e9260142
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_PERSISTENT_RESERVE_OUT IOCTL"]
ms.keywords: IOCTL_STORAGE_PERSISTENT_RESERVE_OUT, IOCTL_STORAGE_PERSISTENT_RESERVE_OUT control, IOCTL_STORAGE_PERSISTENT_RESERVE_OUT control code [Storage Devices], k307_664b87a0-88f2-42ac-851e-b1fbbf36c66a.xml, ntddstor/IOCTL_STORAGE_PERSISTENT_RESERVE_OUT, storage.ioctl_storage_persistent_reserve_out
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_STORAGE_PERSISTENT_RESERVE_OUT
 - ntddstor/IOCTL_STORAGE_PERSISTENT_RESERVE_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_PERSISTENT_RESERVE_OUT
---

# IOCTL_STORAGE_PERSISTENT_RESERVE_OUT IOCTL


## -description

The generic storage class driver (<i>classpnp.sys</i>) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve Out commands. The behavior of the storage device when a Persistent Reserve Out command is received is described in the <a href="https://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification. The IOCTL interface requires the caller to have read/write access to the physical device for Persistent Reserve Out commands. User-mode applications, services, and kernel-mode drivers can use this IOCTL to control persistent reservations. If called from a driver, this IOCTL must be called from a thread running at IRQL < DISPATCH_LEVEL. This IOCTL is defined with FILE_READ_ACCESS and FILE_WRITE_ACCESS, requiring a device handle to have both read and write permissions to issue the Persistent Reserve Out command.

## -ioctlparameters

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_persistent_reserve_command">PERSISTENT_RESERVE_COMMAND</a> structure. You must allocate the buffer from nonpaged pool and must align it correctly for the  target device and adapter.

PR_OUT.ServiceAction can be one of the following:

<ul>
<li>
RESERVATION_ACTION_REGISTER

</li>
<li>
RESERVATION_ACTION_RESERVE

</li>
<li>
RESERVATION_ACTION_RELEASE

</li>
<li>
RESERVATION_ACTION_CLEAR

</li>
<li>
RESERVATION_ACTION_PREEMPT

</li>
<li>
RESERVATION_ACTION_PREEMPT_ABORT

</li>
<li>
RESERVATION_ACTION_REGISTER_IGNORE_EXISTING

</li>
</ul>
PR_OUT.Scope can be one of the following:

<ul>
<li>
RESERVATION_SCOPE_LU

</li>
<li>
RESERVATION_SCOPE_ELEMENT

</li>
</ul>
PR_OUT.Type can be one of the following:

<ul>
<li>
RESERVATION_TYPE_WRITE_EXCLUSIVE

</li>
<li>
RESERVATION_TYPE_EXCLUSIVE

</li>
<li>
RESERVATION_TYPE_WRITE_EXCLUSIVE_REGISTRANTS

</li>
<li>
RESERVATION_TYPE_EXCLUSIVE_REGISTRANTS

</li>
</ul>
PR_OUT.ParameterList is used to hold the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-pro_parameter_list">PRO_PARAMETER_LIST</a> structure. This structure is required and must be contiguous with the rest of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_persistent_reserve_command">PERSISTENT_RESERVE_COMMAND</a> structure.

### -input-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_persistent_reserve_command">PERSISTENT_RESERVE_COMMAND</a> structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero.

The <b>Status</b> field is set to one of the following:




**STATUS_DEVICE_BUSY (ERROR_BUSY)**

The command failed because of a Reservation Conflict (for more information, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification).


**STATUS_INFO_LENGTH_MISMATCH**

The input buffer length for the IOCTL is less than sizeof(PERSISTENT_RESERVE_COMMAND) or the size that is specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_persistent_reserve_command">PERSISTENT_RESERVE_COMMAND</a> data structure is less than sizeof(PERSISTENT_RESERVE_COMMAND).


**STATUS_INVALID_DEVICE_REQUEST (ERROR_INVALID_FUNCTION)**

The I/O control code (IOCTL_STORAGE_PERSISTENT_RESERVE_OUT) is not supported by the storage drivers.


**STATUS_INVALID_PARAMETER (ERROR_INVALID_PARAMETER)**

The input buffer structure is incorrectly sized or populated.


**STATUS_INVALID_USER_BUFFER (ERROR_INVALID_USER_BUFFER)**

The input buffer is not aligned correctly for the device or adapter.  This status could only be returned when a driver sends an IOCTL to the storage stack.  This status will not be returned when a user-mode application sends the IOCTL through the DeviceIoControl API as the I/O Manager automatically aligns the buffers.


**STATUS_IO_DEVICE_ERROR (ERROR_IO_DEVICE)**

The device does not support the Persistent Reserve Out command.


**STATUS_SUCCESS**

The operation was successful.

