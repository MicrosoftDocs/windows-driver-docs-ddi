---
UID: NI:mountmgr.IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
title: IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
author: windows-driver-content
description: This IOCTL informs the mount manager that it should assign drive letters to volumes automatically as they are introduced in the system.
old-location: storage\ioctl_mountmgr_auto_dl_assignments.htm
old-project: storage
ms.assetid: 59ceeaaf-0916-4f0a-a636-624f2f70a64c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS, IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS control code [Storage Devices], k307_ec5f9d47-ffd0-481c-8ce9-fa0465c5b69c.xml, mountmgr/IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS, storage.ioctl_mountmgr_auto_dl_assignments
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
-	IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


This IOCTL informs the mount manager that it should assign drive letters to volumes automatically as they are introduced in the system.


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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

