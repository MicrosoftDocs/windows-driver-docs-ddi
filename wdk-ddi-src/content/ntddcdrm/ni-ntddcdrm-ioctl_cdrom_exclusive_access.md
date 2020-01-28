---
UID: NI:ntddcdrm.IOCTL_CDROM_EXCLUSIVE_ACCESS
title: IOCTL_CDROM_EXCLUSIVE_ACCESS (ntddcdrm.h)
description: The IOCTL_CDROM_EXCLUSIVE_ACCESS request instructs the CD-ROM class driver to:Report the access state of a CD-ROM device.
old-location: storage\ioctl_cdrom_exclusive_access.htm
tech.root: storage
ms.assetid: 449936d8-9257-4044-a38f-e68d8e8d5c68
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_EXCLUSIVE_ACCESS, IOCTL_CDROM_EXCLUSIVE_ACCESS control, IOCTL_CDROM_EXCLUSIVE_ACCESS control code [Storage Devices], k307_d22cebb2-93c2-4eb8-9c2f-6c6c559ee020.xml, ntddcdrm/IOCTL_CDROM_EXCLUSIVE_ACCESS, storage.ioctl_cdrom_exclusive_access
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_EXCLUSIVE_ACCESS"
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
- Ntddcdrm.h
api_name:
- IOCTL_CDROM_EXCLUSIVE_ACCESS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_EXCLUSIVE_ACCESS IOCTL


## -description


The IOCTL_CDROM_EXCLUSIVE_ACCESS request instructs the CD-ROM class driver to:<ul>
<li>
Report the access state of a CD-ROM device. 

</li>
<li>
Lock a CD-ROM device for exclusive access. 

</li>
<li>
Unlock a CD-ROM device for exclusive access. 

</li>
</ul>
A valid FileObject handle must exist in order for this IOCTL to succeed. The FileObject handle protects the system from unexpected application termination or accidental acquisition of an exclusive access lock without subsequent release of the exclusive access lock. A valid FileObject handle is necessary because when an application closes, the CD-ROM class driver will receive CLEANUP and CLOSE I/O Request Packets (IRPs), which it can use to automatically release an exclusive access lock obtained by that handle. This simple method protects against the majority of accidental releases of exclusive access. Any methods used to avoid this functionality may reduce the safety and effectiveness of the exclusive access locking method.




## -ioctlparameters




### -input-buffer

Depending on the operation that the caller requests, the caller must provide one of the following structures as input at <b>Irp->AssociatedIrp.SystemBuffer</b>:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_access">CDROM_EXCLUSIVE_ACCESS</a> (to report the access state of a CD-ROM device)

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_lock">CDROM_EXCLUSIVE_LOCK</a> (to lock a CD-ROM device for exclusive access)

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_access">CDROM_EXCLUSIVE_ACCESS</a> (to unlock a CD-ROM device that the application locked for exclusive access)

</li>
</ul>

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure indicates the size, in bytes, of the user-allocated input buffer.


### -output-buffer

If the caller requests the exclusive access state of the CD-ROM device (<b>RequestType</b> = <b>ExclusiveAccessQueryState</b>), the CD-ROM class driver returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_lock_state">CDROM_EXCLUSIVE_LOCK_STATE</a>-type structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer </b>whose <b>LockState</b> member indicates the access state of the device.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member in the I/O stack location (IO_STACK_LOCATION) indicates the size, in bytes, of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes that are returned. The <b>Status</b> field is set to STATUS_SUCCESS if the request succeeds. 

If the request fails, the <b>Status</b> field might be set to one of the following error messages:




#### -STATUS_ACCESS_DENIED (Windows error code: ERROR_ACCESS_DENIED)

The device is already locked for exclusive access. 


#### -STATUS_BUFFER_TOO_SMALL (Windows error code: ERROR_INSUFFICIENT_BUFFER)

The output buffer was too small for a <b>ExclusiveAccessQueryState</b> request. 


#### -STATUS_INFO_LENGTH_MISMATCH (Windows error code: ERROR_BAD_LENGTH)

The input buffer was too small. 


#### -STATUS_INVALID_DEVICE_REQUEST (Windows error code: ERROR_INVALID_FUNCTION)

The CD-ROM class driver returns this status code when one of the following two errors occurs:

<ul>
<li>
The caller made the request at an IRQL level other than PASSIVE_LEVEL.  

</li>
<li>
The caller sent a request with <b>RequestType</b> = <b>ExclusiveAccessUnlockDevice</b> to unlock a device that is not in exclusive mode. 

</li>
</ul>

#### -STATUS_INVALID_DEVICE_STATE (Windows error code: ERROR_BAD_COMMAND)

The caller attempted to lock a device while the file system driver was mounted on this device, without specifying that the class driver should suspend the check for a mounted file system driver. To suspend the check for a mounted file system driver, the caller must set the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_access">CDROM_EXCLUSIVE_ACCESS</a> to 1. 


#### -STATUS_INVALID_HANDLE (Windows error code: ERROR_INVALID_HANDLE)

The CD-ROM class driver returns this status code when one of the following two errors occurs:

<ul>
<li>
The file object that is required to keep track of the request was not available. The CD-ROM class driver did not receive a request to create a file object from this caller.  

</li>
<li>
The caller sent a request with <b>RequestType</b> = <b>ExclusiveAccessUnlockDevice</b> to unlock a device, even though the caller does not have exclusive access to the device. 

</li>
</ul>

#### -STATUS_INVALID_PARAMETER (Windows error code: ERROR_INVALID_PARAMETER)

The CD-ROM class driver returns this status code when one of the following two errors occurs:

<ul>
<li>
The <b>RequestType</b> that was specified is not a valid member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_exclusive_access_request_type">EXCLUSIVE_ACCESS_REQUEST_TYPE</a>.  

</li>
<li>
The caller name string in the <b>CallerName</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_lock">CDROM_EXCLUSIVE_LOCK</a> violates the naming convention. <b>CallerName</b> must be a <b>NULL</b>-terminated string that contains the following characters: alphanumerics (A - Z, a - z, 0 - 9), spaces, periods, commas, colons (:), semi-colons (;), hyphens (-), and underscores (_). The length of the string must be less than CDROM_EXCLUSIVE_CALLER_LENGTH bytes, including the <b>NULL</b> at the end of the string. 

</li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_access">CDROM_EXCLUSIVE_ACCESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_lock">CDROM_EXCLUSIVE_LOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exclusive_lock_state">CDROM_EXCLUSIVE_LOCK_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_exclusive_access_request_type">EXCLUSIVE_ACCESS_REQUEST_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>
 

 

