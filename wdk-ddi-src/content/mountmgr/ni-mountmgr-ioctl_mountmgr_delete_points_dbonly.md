---
UID: NI:mountmgr.IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
title: IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY (mountmgr.h)
description: This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS.
old-location: storage\ioctl_mountmgr_delete_points_dbonly.htm
tech.root: storage
ms.assetid: 507e42a0-e5f6-4864-a665-d06eb4d1a77b
ms.date: 03/29/2018
keywords: ["IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY, IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY control, IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY control code [Storage Devices], k307_5b02ca9a-551e-42d1-a153-39a6f5d94141.xml, mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY, storage.ioctl_mountmgr_delete_points_dbonly
f1_keywords:
 - "mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY"
 - "IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY"
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
- Mountmgr.h
api_name:
- IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY IOCTL


## -description


This IOCTL is identical in input and output to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>. The difference is that <b>IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY</b> has the side effect of deleting the mount manager database entries for the triples returned. However, the mount manager does not delete the symbolic links corresponding to the database entries.

If the input to this IOCTL is ("\DosDevices\X:", <b>NULL</b>, <b>NULL</b>), where X is the current drive letter for the volume indicated in the input triple, the mount manager adds a special entry to its database indicating that the client does not require a drive letter. On subsequent reboots, the mount manager will not assign a default drive letter to the volume.


## -ioctlparameters




### -input-buffer

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -input-buffer-length

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -output-buffer

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -output-buffer-length

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>
 

 

