---
UID: NI:mountmgr.IOCTL_MOUNTMGR_QUERY_POINTS
title: IOCTL_MOUNTMGR_QUERY_POINTS (mountmgr.h)
description: This IOCTL returns triples that consist of a persistent symbolic link name for the volume (that is, a mount point), a unique ID for the volume, and a nonpersistent device name (such as &#0034;\Device\HarddiskVolume1&#0034;) for the volume.
old-location: storage\ioctl_mountmgr_query_points.htm
tech.root: storage
ms.assetid: 2b7f947c-2fb1-4b59-bf73-a6f0e1478be2
ms.date: 03/29/2018
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

# IOCTL_MOUNTMGR_QUERY_POINTS IOCTL


## -description

This IOCTL returns triples that consist of a persistent symbolic link name for the volume (that is, a mount point), a unique ID for the volume, and a nonpersistent device name (such as "\Device\HarddiskVolume1") for the volume. The input to this IOCTL is a <a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_mount_point">MOUNTMGR_MOUNT_POINT</a> structure that contains a single triple.

If the input triple contains a unique ID or a non-persistent device name, the request retrieves all associated mount points (symbolic links), including the volume GUID pathname and the drive letters. However, if the input triple has a symbolic link, but does not specify either the unique ID or the device name, the request only returns a single triple that contains the symbolic link that was provided in the input, together with the unique ID and the device name. The caller must submit another IOCTL with either the unique ID or the device name to retrieve the remaining mount points.

If the input triple is empty, the mount manager returns the entire mounted device list.

The mount manager returns triples that match as much info as is provided by the caller. If the caller submits the unique ID, the mount manager returns all triples with that unique ID. If the caller inputs the volume pathname or a drive letter as the symbolic link name, the mount manager returns only the triple for the symbolic link. There is one entry per symbolic link. If the caller inputs a device pathname, the mount manager returns only the triples for that device pathname. If the caller inputs a unique ID and a symbolic link, again, the mount manager returns only one entry for that symbolic link. A caller would do this to get the device pathname. If the caller inputs no device pathname, unique ID or symbolic link, the mount manager returns all entries/triples.

## -ioctlparameters

### -input-buffer

The mount manager client initializes the <a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_mount_point">MOUNTMGR_MOUNT_POINT</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. Immediately following this structure, the MM client loads the symbolic link name, the unique ID and the device name, in that order.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_MOUNT_POINT).

### -output-buffer

The mount manager initializes a variable-length structure of type <a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_mount_points">MOUNTMGR_MOUNT_POINTS</a>, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. The mount manager inserts the mount points, associated with the indicated volume, at the address pointed to by the <i>MountPoints[]</i> member of this structure. Each mount point is represented by a MOUNTMGR_MOUNT_POINT structure as defined in the <b>Input</b> section for this IOCTL.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If neither the unique ID nor the nonpersistent device name are found in the volumes mounted device list, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_MOUNT_POINT), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If <b>InputBufferLength</b> is less than the total length of the three input ID strings, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If <b>OutputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_MOUNT_POINT), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If <b>OutputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_MOUNT_POINTS) plus the sum of the sizes of the mount point triples, the <b>Status</b> field is set to STATUS_BUFFER_OVERFLOW.

If any of the three strings contained within any of the triples is aligned on an odd address (for example, address & 01 != 0), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

## -see-also

<a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_mount_points">MOUNTMGR_MOUNT_POINTS</a>