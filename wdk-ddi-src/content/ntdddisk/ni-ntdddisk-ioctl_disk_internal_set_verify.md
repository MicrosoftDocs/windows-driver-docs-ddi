---
UID: NI:ntdddisk.IOCTL_DISK_INTERNAL_SET_VERIFY
title: IOCTL_DISK_INTERNAL_SET_VERIFY
author: windows-driver-content
description: Allows a driver to set the verify bit on a disk device object if the mode of the caller is kernel mode.
old-location: storage\ioctl_disk_internal_set_verify.htm
old-project: storage
ms.assetid: ddfca68f-142e-4e6a-9307-04a3136a4135
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_INTERNAL_SET_VERIFY, IOCTL_DISK_INTERNAL_SET_VERIFY control code [Storage Devices], k307_d97d4ec3-63c0-4041-9953-8727b1b82e66.xml, ntdddisk/IOCTL_DISK_INTERNAL_SET_VERIFY, storage.ioctl_disk_internal_set_verify
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
-	IOCTL_DISK_INTERNAL_SET_VERIFY
product:
- Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_INTERNAL_SET_VERIFY IOCTL


## -description



Allows a driver to set the verify bit on a disk device object if the mode of the caller is kernel mode.




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

The <b>Status</b> field is set to STATUS_SUCCESS. If the mode of the requester is not kernel mode, the requested operation is not performed, but STATUS_SUCCESS is still returned.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560378">IOCTL_DISK_INTERNAL_CLEAR_VERIFY</a>
 

 

