---
UID: NI:ntdddisk.IOCTL_DISK_IS_CLUSTERED
title: IOCTL_DISK_IS_CLUSTERED (ntdddisk.h)
description: Allows a driver or application to determine if a disk is clustered.
old-location: storage\ioctl_disk_is_clustered.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_IS_CLUSTERED IOCTL"]
ms.keywords: IOCTL_DISK_IS_CLUSTERED, IOCTL_DISK_IS_CLUSTERED control, IOCTL_DISK_IS_CLUSTERED control code [Storage Devices], k307_a812ef4f-f10c-4d75-aaf8-a3ad4d41703e.xml, ntdddisk/IOCTL_DISK_IS_CLUSTERED, storage.ioctl_disk_is_clustered
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
 - IOCTL_DISK_IS_CLUSTERED
 - ntdddisk/IOCTL_DISK_IS_CLUSTERED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_IS_CLUSTERED
---

# IOCTL_DISK_IS_CLUSTERED IOCTL


## -description

Allows a driver or application to determine if a disk is clustered.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a Boolean value, with <b>TRUE</b> indicating that the disk is clustered.

### -output-buffer-length

Length of a Boolean.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.
