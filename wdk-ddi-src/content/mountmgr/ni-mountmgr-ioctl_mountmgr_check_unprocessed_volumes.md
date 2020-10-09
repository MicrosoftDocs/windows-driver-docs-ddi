---
UID: NI:mountmgr.IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
title: IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES (mountmgr.h)
description: When a volume arrives in the system, it registers for the MOUNTDEV_MOUNTED_DEVICE_GUID interface class and the mount manager receives a Plug and Play notification (see Mount Manager I/O Control Codes for a discussion of this process).
old-location: storage\ioctl_mountmgr_check_unprocessed_volumes.htm
tech.root: storage
ms.assetid: 39f486b4-a22e-473b-9a0d-ba2c1046995a
ms.date: 03/29/2018
keywords: ["IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES, IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES control, IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES control code [Storage Devices], k307_eb4defdf-c3d0-41b6-8bd4-3ef1dbd3f795.xml, mountmgr/IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES, storage.ioctl_mountmgr_check_unprocessed_volumes
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
 - IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
 - mountmgr/IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
---

# IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES IOCTL


## -description

When a volume arrives in the system, it registers for the MOUNTDEV_MOUNTED_DEVICE_GUID interface class and the mount manager receives a Plug and Play notification (see <a href="/windows-hardware/drivers/ddi/index">Mount Manager I/O Control Codes</a> for a discussion of this process). When the mount manager receives this notification, it queries the client driver that manages the volume for the volume's unique ID. In some cases, however, particularly with clusters, the client notifies the mount manager of the arrival of its volume, but then does not respond when queried for the volume's unique ID. The mount manager keeps these volumes in a <i>dead mounted device </i>list. Clients can use the IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES IOCTL to request that the mount manager rescan its dead mounted device list and make another attempt to query the clients on the list for the unique IDs of their respective volumes.

This IOCTL is used primarily for cluster support.

## -ioctlparameters

### -input-buffer

None

### -input-buffer-length

None

### -output-buffer

None

### -output-buffer-length

None

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.