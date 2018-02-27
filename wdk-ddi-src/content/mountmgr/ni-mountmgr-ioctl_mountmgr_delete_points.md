---
UID: NI:mountmgr.IOCTL_MOUNTMGR_DELETE_POINTS
title: IOCTL_MOUNTMGR_DELETE_POINTS
author: windows-driver-content
description: This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned.
old-location: storage\ioctl_mountmgr_delete_points.htm
old-project: storage
ms.assetid: c11d801a-4870-42c4-9374-e0f849d57cde
ms.author: windowsdriverdev
ms.date: 2/24/2018
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


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


This IOCTL is identical in input and output to <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned.

If the input to this IOCTL is ("\DosDevices\X:", <b>NULL</b>, <b>NULL</b>) where X is the current drive letter for the volume indicated in the input triple, the mount manager adds a special entry to its database indicating that the client does not require a drive letter. On subsequent reboots, the mount manager will not assign a default drive letter to the volume.


## -ioctlparameters




### -input-buffer

See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -input-buffer-length

See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -output-buffer

See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -output-buffer-length

See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_DELETE_POINTS control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

