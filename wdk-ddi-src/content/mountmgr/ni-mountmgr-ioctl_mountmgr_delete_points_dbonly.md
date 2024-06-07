---
UID: NI:mountmgr.IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
title: IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY IOCTL.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY, IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY control, IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY control code [Storage Devices], k307_5b02ca9a-551e-42d1-a153-39a6f5d94141.xml, mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY, storage.ioctl_mountmgr_delete_points_dbonly
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
 - IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
 - mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
---

## -description

This IOCTL is identical in input and output to [**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md). The difference is that **IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY** has the side effect of deleting the mount manager database entries for the triples returned. However, the mount manager does not delete the symbolic links corresponding to the database entries.

If the input to this IOCTL is ("\DosDevices\X:", NULL, NULL), where X is the current drive letter for the volume indicated in the input triple, the mount manager adds a special entry to its database indicating that the client does not require a drive letter. On subsequent reboots, the mount manager will not assign a default drive letter to the volume.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

See [**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md).

### -input-buffer-length

See [**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md).

### -output-buffer

See [**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md).

### -output-buffer-length

See [**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md).

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

See [**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md).

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**IOCTL_MOUNTMGR_QUERY_POINTS**](ni-mountmgr-ioctl_mountmgr_query_points.md)
