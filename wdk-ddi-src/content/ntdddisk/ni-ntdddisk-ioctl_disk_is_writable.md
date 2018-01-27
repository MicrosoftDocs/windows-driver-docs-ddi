---
UID: NI:ntdddisk.IOCTL_DISK_IS_WRITABLE
title: IOCTL_DISK_IS_WRITABLE
author: windows-driver-content
description: Determines whether a disk is writable.
old-location: storage\ioctl_disk_is_writable.htm
old-project: storage
ms.assetid: 073dd5d4-d6b9-42c8-adb2-1d6c53f2a352
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_disk_is_writable, IOCTL_DISK_IS_WRITABLE control code [Storage Devices], IOCTL_DISK_IS_WRITABLE, ntdddisk/IOCTL_DISK_IS_WRITABLE, k307_b5d259a8-bf23-4475-98ce-69c87b3de52c.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntdddisk.h
apiname: 
-	IOCTL_DISK_IS_WRITABLE
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_IS_WRITABLE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Determines whether a disk is writable.




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

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_MEDIA_WRITE_PROTECTED.

