---
UID: NI:hidclass.IOCTL_HID_DISABLE_SECURE_READ
title: IOCTL_HID_DISABLE_SECURE_READ (hidclass.h)
description: The IOCTL_HID_DISABLE_SECURE_READ request cancels an IOCTL_HID_ENABLE_SECURE_READ request for a HID collection.
old-location: hid\ioctl_hid_disable_secure_read.htm
tech.root: hid
ms.assetid: 7e63110d-6383-4e57-a66a-7d5190a98314
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_DISABLE_SECURE_READ, IOCTL_HID_DISABLE_SECURE_READ control, IOCTL_HID_DISABLE_SECURE_READ control code [Human Input Devices], hid.ioctl_hid_disable_secure_read, hidclass/IOCTL_HID_DISABLE_SECURE_READ, hidioreq_a1eddca2-c66a-4311-ac07-71f5880cbffb.xml
ms.topic: ioctl
f1_keywords:
 - "hidclass/IOCTL_HID_DISABLE_SECURE_READ"
req.header: hidclass.h
req.include-header: Hidclass.h
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
- hidclass.h
api_name:
- IOCTL_HID_DISABLE_SECURE_READ
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_DISABLE_SECURE_READ IOCTL


## -description


The IOCTL_HID_DISABLE_SECURE_READ request cancels an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_enable_secure_read">IOCTL_HID_ENABLE_SECURE_READ</a> request for a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID collection</a>. Only a "trusted" user-mode application (an application with SeTcbPrivilege privileges) can successfully use this request. Kernel-mode drivers have SeTcbPrivilege privileges by default, but user-mode applications do not.

For information about how to use enable and disable secure read requests to enforce a secure read for a collection, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/enforcing-a-secure-read-for-a-hid-collection">Enforcing a Secure Read For a HID Collection</a>.


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

The HID class driver sets the <b>Status</b> member of <b>Irp->IoStatus</b> to STATUS_SUCCESS if the requester has SeTcbPrivilege privileges and the file is valid. Otherwise, it is set to STATUS_PRIVILEGE_NOT_HELD.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_disable_secure_read">IOCTL_HID_DISABLE_SECURE_READ</a>
 

 

