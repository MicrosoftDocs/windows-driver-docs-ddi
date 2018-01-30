---
UID: NS:mountmgr._MOUNTMGR_VOLUME_MOUNT_POINT
title: "_MOUNTMGR_VOLUME_MOUNT_POINT"
author: windows-driver-content
description: The MOUNTMGR_VOLUME_MOUNT_POINT structure is used in conjunction with the IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED request to inform the mount manager that a volume mount point has been created.
old-location: storage\mountmgr_volume_mount_point.htm
old-project: storage
ms.assetid: 2a267992-b4d3-49e1-bb80-3849220f0d1f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MOUNTMGR_VOLUME_MOUNT_POINT structure [Storage Devices], *PMOUNTMGR_VOLUME_MOUNT_POINT, _MOUNTMGR_VOLUME_MOUNT_POINT, MOUNTMGR_VOLUME_MOUNT_POINT, mountmgr/MOUNTMGR_VOLUME_MOUNT_POINT, PMOUNTMGR_VOLUME_MOUNT_POINT structure pointer [Storage Devices], mountmgr/PMOUNTMGR_VOLUME_MOUNT_POINT, storage.mountmgr_volume_mount_point, PMOUNTMGR_VOLUME_MOUNT_POINT, structs-mntmgr_afa5831e-a33d-4fb6-a67b-b0b4f459e19b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mountmgr.h
apiname:
-	MOUNTMGR_VOLUME_MOUNT_POINT
product: Windows
targetos: Windows
req.typenames: "*PMOUNTMGR_VOLUME_MOUNT_POINT, MOUNTMGR_VOLUME_MOUNT_POINT"
---

# _MOUNTMGR_VOLUME_MOUNT_POINT structure


## -description


The MOUNTMGR_VOLUME_MOUNT_POINT structure is used in conjunction with the <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_volume_mount_point_created.md">IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED</a> request to inform the mount manager that a volume mount point has been created. 


## -syntax


````
typedef struct _MOUNTMGR_VOLUME_MOUNT_POINT {
  USHORT SourceVolumeNameOffset;
  USHORT SourceVolumeNameLength;
  USHORT TargetVolumeNameOffset;
  USHORT TargetVolumeNameLength;
} MOUNTMGR_VOLUME_MOUNT_POINT, *PMOUNTMGR_VOLUME_MOUNT_POINT;
````


## -struct-fields




### -field SourceVolumeNameOffset

Contains an offset, in bytes, into the output buffer where the name of the mount point is located. 


### -field SourceVolumeNameLength

Contains the length, in bytes, of the mount point name. 


### -field TargetVolumeNameOffset

Contains an offset, in bytes, into the output buffer where the unique (persistent) volume name of the target device is located. 


### -field TargetVolumeNameLength

Contains the length, in bytes, of the target name. 


## -remarks


Mount point names must contain the full path of a mount point object name in the system object tree. For example: "\DosDevices\E:\FilesysD\mnt". For an explanation of unique volume names and how the mount manager uses them, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 



## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_volume_mount_point_created.md">IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTMGR_VOLUME_MOUNT_POINT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

