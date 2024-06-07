---
UID: NS:mountmgr._MOUNTDEV_NAME
title: MOUNTDEV_NAME (mountmgr.h)
description: Learn about the MOUNTDEV_NAME structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTDEV_NAME structure"]
ms.keywords: "*PMOUNTDEV_NAME, MOUNTDEV_NAME, MOUNTDEV_NAME structure [Storage Devices], PMOUNTDEV_NAME, PMOUNTDEV_NAME structure pointer [Storage Devices], _MOUNTDEV_NAME, mountmgr/MOUNTDEV_NAME, mountmgr/PMOUNTDEV_NAME, storage.mountdev_name, structs-mntmgr_b7eec4f5-e4fc-4931-82e5-c6ac5cd4b48f.xml"
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
req.typenames: MOUNTDEV_NAME, *PMOUNTDEV_NAME
f1_keywords:
 - _MOUNTDEV_NAME
 - mountmgr/_MOUNTDEV_NAME
 - PMOUNTDEV_NAME
 - mountmgr/PMOUNTDEV_NAME
 - MOUNTDEV_NAME
 - mountmgr/MOUNTDEV_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTDEV_NAME
 - PMOUNTDEV_NAME
 - MOUNTDEV_NAME
---

## -description

The **MOUNTDEV_NAME** structure holds the name of a device.

## -struct-fields

### -field NameLength

Contains the length of the name, in bytes.

### -field Name

Contains a variable-sized array of wide characters that holds the name of the device mount point. The name may be a nonpersistent target name such as "\Device\HarddiskVolume1", a persistent symbolic link name such as a drive letter, "\DosDevices\D:", or a mount point such as "\DosDevices\E:\FilesysD\mnt".

## -remarks

As a best practice, the implementer must not thread-synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[IOCTL_MOUNTDEV_LINK_CREATED](../mountdev/ni-mountdev-ioctl_mountdev_link_created.md)

[IOCTL_MOUNTDEV_LINK_DELETED](../mountdev/ni-mountdev-ioctl_mountdev_link_deleted.md)

[IOCTL_MOUNTDEV_QUERY_DEVICE_NAME](./ni-mountmgr-ioctl_mountdev_query_device_name.md)
