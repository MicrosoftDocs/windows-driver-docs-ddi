---
UID: NI:ntdddisk.IOCTL_DISK_INTERNAL_SET_VERIFY
title: IOCTL_DISK_INTERNAL_SET_VERIFY (ntdddisk.h)
description: Allows a driver to set the verify bit on a disk device object if the mode of the caller is kernel mode.
old-location: storage\ioctl_disk_internal_set_verify.htm
tech.root: storage
ms.assetid: ddfca68f-142e-4e6a-9307-04a3136a4135
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_INTERNAL_SET_VERIFY IOCTL"]
ms.keywords: IOCTL_DISK_INTERNAL_SET_VERIFY, IOCTL_DISK_INTERNAL_SET_VERIFY control, IOCTL_DISK_INTERNAL_SET_VERIFY control code [Storage Devices], k307_d97d4ec3-63c0-4041-9953-8727b1b82e66.xml, ntdddisk/IOCTL_DISK_INTERNAL_SET_VERIFY, storage.ioctl_disk_internal_set_verify
f1_keywords:
 - "ntdddisk/IOCTL_DISK_INTERNAL_SET_VERIFY"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntdddisk.h
api_name:
- IOCTL_DISK_INTERNAL_SET_VERIFY
product:
- Windows
targetos: Windows
req.typenames: 
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








### -inout-buffer-length








### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS. If the mode of the requester is not kernel mode, the requested operation is not performed, but STATUS_SUCCESS is still returned.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_internal_clear_verify">IOCTL_DISK_INTERNAL_CLEAR_VERIFY</a>
 

 

