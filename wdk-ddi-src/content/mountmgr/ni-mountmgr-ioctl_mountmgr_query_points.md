---
UID: NI:mountmgr.IOCTL_MOUNTMGR_QUERY_POINTS
title: IOCTL_MOUNTMGR_QUERY_POINTS (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_QUERY_POINTS IOCTL.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTMGR_QUERY_POINTS IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_QUERY_POINTS, IOCTL_MOUNTMGR_QUERY_POINTS control, IOCTL_MOUNTMGR_QUERY_POINTS control code [Storage Devices], k307_2d7b44e3-c40f-4626-aad0-5e1cf8843685.xml, mountmgr/IOCTL_MOUNTMGR_QUERY_POINTS, storage.ioctl_mountmgr_query_points
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
 - IOCTL_MOUNTMGR_QUERY_POINTS
 - mountmgr/IOCTL_MOUNTMGR_QUERY_POINTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_QUERY_POINTS
---

## -description

This IOCTL returns triples that consist of a persistent symbolic link name for the volume (that is, a mount point), a unique ID for the volume, and a nonpersistent device name (such as "\Device\HarddiskVolume1") for the volume. The input to this IOCTL is a [**MOUNTMGR_MOUNT_POINT**](ns-mountmgr-_mountmgr_mount_point.md) structure that contains a single triple.

If the input triple contains a unique ID or a non-persistent device name, the request retrieves all associated mount points (symbolic links), including the volume GUID pathname and the drive letters. However, if the input triple has a symbolic link, but does not specify either the unique ID or the device name, the request only returns a single triple that contains the symbolic link that was provided in the input, together with the unique ID and the device name. The caller must submit another IOCTL with either the unique ID or the device name to retrieve the remaining mount points.

If the input triple is empty, the mount manager returns the entire mounted device list.

The mount manager returns triples that match as much info as is provided by the caller. If the caller submits the unique ID, the mount manager returns all triples with that unique ID. If the caller inputs the volume pathname or a drive letter as the symbolic link name, the mount manager returns only the triple for the symbolic link. There is one entry per symbolic link. If the caller inputs a device pathname, the mount manager returns only the triples for that device pathname. If the caller inputs a unique ID and a symbolic link, again, the mount manager returns only one entry for that symbolic link. A caller would do this to get the device pathname. If the caller inputs no device pathname, unique ID or symbolic link, the mount manager returns all entries/triples.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

The mount manager client initializes the [**MOUNTMGR_MOUNT_POINT**](ns-mountmgr-_mountmgr_mount_point.md) structure at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**. Immediately following this structure, the MM client loads the symbolic link name, the unique ID and the device name, in that order.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_MOUNT_POINT)```.

### -output-buffer

The mount manager initializes a variable-length structure of type [**MOUNTMGR_MOUNT_POINTS**](ns-mountmgr-_mountmgr_mount_points.md) at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**. The mount manager inserts the mount points, associated with the indicated volume, at the address pointed to by the **MountPoints[]** member of this structure. Each mount point is represented by a MOUNTMGR_MOUNT_POINT structure as defined in the **Input** section for this IOCTL.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_MOUNT_POINTS)```.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

If the operation is successful, the **Status** field is set to STATUS_SUCCESS.

If neither the unique ID nor the nonpersistent device name are found in the volumes mounted device list, the **Status** field is set to STATUS_INVALID_PARAMETER.

If **InputBufferLength** is less than ```sizeof(MOUNTMGR_MOUNT_POINT)```, the **Status** field is set to STATUS_INVALID_PARAMETER.

If **InputBufferLength** is less than the total length of the three input ID strings, the **Status** field is set to STATUS_INVALID_PARAMETER.

If **OutputBufferLength** is less than ```sizeof(MOUNTMGR_MOUNT_POINT)```, the **Status** field is set to STATUS_INVALID_PARAMETER.

If **OutputBufferLength** is less than ```sizeof(MOUNTMGR_MOUNT_POINTS)``` plus the sum of the sizes of the mount point triples, the **Status** field is set to STATUS_BUFFER_OVERFLOW.

If any of the three strings contained within any of the triples is aligned on an odd address (for example, address & 01 != 0), the **Status** field is set to STATUS_INVALID_PARAMETER.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTMGR_MOUNT_POINTS**](ns-mountmgr-_mountmgr_mount_points.md)
