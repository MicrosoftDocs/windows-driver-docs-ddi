---
UID: NI:mountmgr.IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
title: IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS IOCTL.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS, IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS control, IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS control code [Storage Devices], k307_ec5f9d47-ffd0-481c-8ce9-fa0465c5b69c.xml, mountmgr/IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS, storage.ioctl_mountmgr_auto_dl_assignments
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
 - IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
 - mountmgr/IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
---

## -description

IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS informs the mount manager that it should assign drive letters to volumes automatically as they are introduced in the system.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

If the operation is successful, the **Status** field is set to STATUS_SUCCESS.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).
