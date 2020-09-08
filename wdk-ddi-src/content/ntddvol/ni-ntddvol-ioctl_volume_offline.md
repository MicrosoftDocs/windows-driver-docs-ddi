---
UID: NI:ntddvol.IOCTL_VOLUME_OFFLINE
title: IOCTL_VOLUME_OFFLINE (ntddvol.h)
description: The IOCTL_VOLUME_OFFLINE IOCTL puts the volume in an OFFLINE state, which is a state where read and write operations will fail.
old-location: storage\ioctl_volume_offline.htm
tech.root: storage
ms.assetid: 09a1faa7-9ce4-44ac-afb0-27ffeabc9d71
ms.date: 03/29/2018
keywords: ["IOCTL_VOLUME_OFFLINE IOCTL"]
ms.keywords: IOCTL_VOLUME_OFFLINE, IOCTL_VOLUME_OFFLINE control, IOCTL_VOLUME_OFFLINE control code [Storage Devices], k307_34afa35b-2242-4ec3-9e42-f50e9837fab0.xml, ntddvol/IOCTL_VOLUME_OFFLINE, storage.ioctl_volume_offline
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
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
 - IOCTL_VOLUME_OFFLINE
 - ntddvol/IOCTL_VOLUME_OFFLINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvol.h
api_name:
 - IOCTL_VOLUME_OFFLINE
---

# IOCTL_VOLUME_OFFLINE IOCTL


## -description

The <b>IOCTL_VOLUME_OFFLINE</b> IOCTL puts the volume in an OFFLINE state, which is a state where read and write operations will fail. The requests will not be passed down to the physical disk until a subsequent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_online">IOCTL_VOLUME_ONLINE</a> is received.

A common use for <b>IOCTL_VOLUME_OFFLINE</b> is a case in which one application or driver wants to prevent a volume from being remounted by a call to open the volume from a second application or driver while the volume is in the process of being removed by the first application or driver. For example, before masking a Logical Unit Number (LUN), the volumes on the LUN should be locked (optional), dismounted, taken offline, and uninstalled. Now the LUN can be masked without causing Plug and Play (PnP) surprise removal events to be logged for the volumes and the disk itself. Without the call to take the volume offline, after the handle that is used to dismount it is closed, the volume can then be remounted by a call to open it from another application or driver, if it occurred before the call to uninstall the volume. A call to open a volume succeeds on an offline volume, but I/O directed toward an offline volume fails. Taking a volume offline has no effect on disk I/O (if the application or driver opened a handle to the disk), but stops volume I/O (if the application or driver opened a handle to the volume).

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Status</b> member is set to STATUS_SUCCESS.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_online">IOCTL_VOLUME_ONLINE</a>

