---
UID: NS:mountmgr._MOUNTDEV_NAME
title: _MOUNTDEV_NAME (mountmgr.h)
description: The MOUNTDEV_NAME structure holds the name of a device.
old-location: storage\mountdev_name.htm
tech.root: storage
ms.assetid: 26f5e98d-0709-403a-abcf-776c117d4f38
ms.date: 03/29/2018
ms.keywords: "*PMOUNTDEV_NAME, MOUNTDEV_NAME, MOUNTDEV_NAME structure [Storage Devices], PMOUNTDEV_NAME, PMOUNTDEV_NAME structure pointer [Storage Devices], _MOUNTDEV_NAME, mountmgr/MOUNTDEV_NAME, mountmgr/PMOUNTDEV_NAME, storage.mountdev_name, structs-mntmgr_b7eec4f5-e4fc-4931-82e5-c6ac5cd4b48f.xml"
f1_keywords:
 - "mountmgr/MOUNTDEV_NAME"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mountmgr.h
api_name:
- MOUNTDEV_NAME
product:
- Windows
targetos: Windows
req.typenames: MOUNTDEV_NAME, *PMOUNTDEV_NAME
---

# _MOUNTDEV_NAME structure

## -description

The MOUNTDEV_NAME structure holds the name of a device. 

## -struct-fields

### -field NameLength

Contains the length of the name, in bytes.

### -field Name

Contains a variable-sized array of wide characters that holds the name of the device mount point. The name may be a nonpersistent target name such as "\Device\HarddiskVolume1", a persistent symbolic link name such as a drive letter, "\DosDevices\D:", or a mount point such as "\DosDevices\E:\FilesysD\mnt".

## -remarks

As a best practice, the implementer must not thread-synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

## -see-also

[IOCTL_MOUNTDEV_LINK_CREATED](https://docs.microsoft.com/windows-hardware/drivers/ddi/mountdev/ni-mountdev-ioctl_mountdev_link_created)

[IOCTL_MOUNTDEV_LINK_DELETED](https://docs.microsoft.com/windows-hardware/drivers/ddi/mountdev/ni-mountdev-ioctl_mountdev_link_deleted)

[IOCTL_MOUNTDEV_QUERY_DEVICE_NAME](https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountdev_query_device_name)
