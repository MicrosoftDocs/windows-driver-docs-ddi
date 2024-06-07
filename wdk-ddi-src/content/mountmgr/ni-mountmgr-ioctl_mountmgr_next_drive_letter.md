---
UID: NI:mountmgr.IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
title: IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER IOCTL.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER, IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER control, IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER control code [Storage Devices], k307_c77572b5-04ff-453d-91a4-9f58c65930e0.xml, mountmgr/IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER, storage.ioctl_mountmgr_next_drive_letter
req.header: mountmgr.h
req.include-header: Mountmgr.h
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
 - IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
 - mountmgr/IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
---


## -description

This IOCTL checks to see if the given volume has a drive letter. If it already has a drive letter, or if the volume has a special mount manager database entry indicating that it does not require a drive letter, this routine returns the current drive letter (if there is one) and does nothing. If the given volume does not have a drive letter and does not have a special mount manager database entry indicating that it does not require a drive letter, the next available drive letter is assigned to the volume. If the volume's nonpersistent device name begins with "\Device\Floppy", the mount manager will check for available drive letters starting with the letter "A." If the volume name begins with "\Device\CdRom" the mount manager will check for available drive letters starting with drive letter "D." In all other cases, the mount manager starts with drive letter "C."

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

The mount manager client initializes the [**MOUNTMGR_DRIVE_LETTER_TARGET**](ns-mountmgr-_mountmgr_drive_letter_target.md) structure at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**. The client must insert the name of the target volume at the address pointed to by the **DeviceName[]** member of this structure. The target volume name is the name of the nonpersistent device object associated with the volume (for example, "\Device\HarddiskVolume1").

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_DRIVE_LETTER_TARGET)```.

### -output-buffer

The mount manager inserts either the current drive letter or the newly assigned drive letter (see previous discussion) in the [**MOUNTMGR_DRIVE_LETTER_INFORMATION**](ns-mountmgr-_mountmgr_drive_letter_information.md) structure at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_DRIVE_LETTER_INFORMATION)```.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

If the operation is successful , the **Status** field is set to STATUS_SUCCESS.

If **InputBufferLength** is less than ```sizeof(MOUNTMGR_DRIVE_LETTER_TARGET)``` or if **OutputBufferLength** is less than ```sizeof(MOUNTMGR_DRIVE_LETTER_INFORMATION)```, the **Status** field is set to STATUS_INVALID_PARAMETER.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTMGR_DRIVE_LETTER_TARGET**](ns-mountmgr-_mountmgr_drive_letter_target.md)
