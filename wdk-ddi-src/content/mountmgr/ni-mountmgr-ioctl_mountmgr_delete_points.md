---
UID: NI:mountmgr.IOCTL_MOUNTMGR_DELETE_POINTS
title: IOCTL_MOUNTMGR_DELETE_POINTS (mountmgr.h)
description: This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned.
old-location: storage\ioctl_mountmgr_delete_points.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_MOUNTMGR_DELETE_POINTS IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_DELETE_POINTS, IOCTL_MOUNTMGR_DELETE_POINTS control, IOCTL_MOUNTMGR_DELETE_POINTS control code [Storage Devices], k307_c218ecf5-b934-4cad-934c-738cde9bff2b.xml, mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS, storage.ioctl_mountmgr_delete_points
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
 - IOCTL_MOUNTMGR_DELETE_POINTS
 - mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_DELETE_POINTS
---

# IOCTL_MOUNTMGR_DELETE_POINTS IOCTL


## -description

This IOCTL is identical in input and output to <a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned.

If the input to this IOCTL is ("\DosDevices\X:", <b>NULL</b>, <b>NULL</b>) where X is the current drive letter for the volume indicated in the input triple, the mount manager adds a special entry to its database indicating that the client does not require a drive letter. On subsequent reboots, the mount manager will not assign a default drive letter to the volume.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

See <a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### -input-buffer-length

See <a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### -output-buffer

See <a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### -output-buffer-length

See <a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

See <a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>
