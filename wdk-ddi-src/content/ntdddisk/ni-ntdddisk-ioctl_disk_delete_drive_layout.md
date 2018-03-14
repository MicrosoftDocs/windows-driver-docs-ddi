---
UID: NI:ntdddisk.IOCTL_DISK_DELETE_DRIVE_LAYOUT
title: IOCTL_DISK_DELETE_DRIVE_LAYOUT
author: windows-driver-content
description: Removes partition information from the disk.
old-location: storage\ioctl_disk_delete_drive_layout.htm
old-project: storage
ms.assetid: 787fa1ce-5305-4159-8710-3c6971133c4c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DISK_DELETE_DRIVE_LAYOUT, IOCTL_DISK_DELETE_DRIVE_LAYOUT control code [Storage Devices], k307_7319c33d-d8ab-438c-9908-ac380bff54b5.xml, ntdddisk/IOCTL_DISK_DELETE_DRIVE_LAYOUT, storage.ioctl_disk_delete_drive_layout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_DELETE_DRIVE_LAYOUT
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_DELETE_DRIVE_LAYOUT IOCTL


## -description



Removes partition information from the disk. If the partition style of the disk is Master Boot Record (MBR), sector 0 of the disk is wiped clean except for the bootstrap code. All signatures, such as the AA55 boot signature and the NTFT disk signature, will be removed. If the partition style of the disk is GUID Partition Table (GPT), the primary partition table header in sector 1 and the backup partition table in the last sector of the disk are wiped clean. This operation can be used to generate so-called "superfloppies" that contain a file system starting at the first sector of the disk rather than in a partition on the disk.




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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

