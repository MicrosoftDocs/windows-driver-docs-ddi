---
UID: NI:mountmgr.IOCTL_MOUNTMGR_DELETE_POINTS
title: IOCTL_MOUNTMGR_DELETE_POINTS
author: windows-driver-content
description: This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned.
old-location: storage\ioctl_mountmgr_delete_points.htm
old-project: storage
ms.assetid: c11d801a-4870-42c4-9374-e0f849d57cde
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_MOUNTMGR_DELETE_POINTS, IOCTL_MOUNTMGR_DELETE_POINTS control code [Storage Devices], k307_c218ecf5-b934-4cad-934c-738cde9bff2b.xml, mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS, storage.ioctl_mountmgr_delete_points
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Mountmgr.h
api_name:
-	IOCTL_MOUNTMGR_DELETE_POINTS
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_DELETE_POINTS IOCTL


## -description


This IOCTL is identical in input and output to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned.

If the input to this IOCTL is ("\DosDevices\X:", <b>NULL</b>, <b>NULL</b>) where X is the current drive letter for the volume indicated in the input triple, the mount manager adds a special entry to its database indicating that the client does not require a drive letter. On subsequent reboots, the mount manager will not assign a default drive letter to the volume.


## -ioctlparameters




### -input-buffer

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -input-buffer-length

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -output-buffer

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -output-buffer-length

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>
 

 

