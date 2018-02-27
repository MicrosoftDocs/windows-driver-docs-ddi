---
UID: NS:mountmgr._MOUNTMGR_MOUNT_POINTS
title: "_MOUNTMGR_MOUNT_POINTS"
author: windows-driver-content
description: The MOUNTMGR_MOUNT_POINTS structure is used by mount manager to send a client the list of mount points associated with a device.
old-location: storage\mountmgr_mount_points.htm
old-project: storage
ms.assetid: e85c0d92-d989-4afc-8516-c63535d2c728
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMOUNTMGR_MOUNT_POINTS, MOUNTMGR_MOUNT_POINTS, MOUNTMGR_MOUNT_POINTS structure [Storage Devices], PMOUNTMGR_MOUNT_POINTS, PMOUNTMGR_MOUNT_POINTS structure pointer [Storage Devices], _MOUNTMGR_MOUNT_POINTS, mountmgr/MOUNTMGR_MOUNT_POINTS, mountmgr/PMOUNTMGR_MOUNT_POINTS, storage.mountmgr_mount_points, structs-mntmgr_844fdf51-1324-4b1d-b68f-abba5f471652.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mountmgr.h
api_name:
-	MOUNTMGR_MOUNT_POINTS
product: Windows
targetos: Windows
req.typenames: MOUNTMGR_MOUNT_POINTS, *PMOUNTMGR_MOUNT_POINTS
---

# _MOUNTMGR_MOUNT_POINTS structure


## -description


The MOUNTMGR_MOUNT_POINTS structure is used by mount manager to send a client the list of mount points associated with a device.


## -syntax


````
typedef struct _MOUNTMGR_MOUNT_POINTS {
  ULONG                Size;
  ULONG                NumberOfMountPoints;
  MOUNTMGR_MOUNT_POINT MountPoints[1];
} MOUNTMGR_MOUNT_POINTS, *PMOUNTMGR_MOUNT_POINTS;
````


## -struct-fields




### -field Size

Contains the size, in bytes, of the output buffer. 


### -field NumberOfMountPoints

Contains the number of mount points that the mount manager is returning. 


### -field MountPoints

Contains an array of elements of type MOUNTMGR_MOUNT_POINT that contain information about each mount point associated with the device.


## -remarks



For a discussion of the different between symbolic links, unique IDs, and nonpersistent device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTMGR_MOUNT_POINTS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

