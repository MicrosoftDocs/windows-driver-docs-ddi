---
UID: NI:ntdddisk.IOCTL_DISK_INTERNAL_CLEAR_VERIFY
title: IOCTL_DISK_INTERNAL_CLEAR_VERIFY
author: windows-driver-content
description: Allows a driver to clear the verify bit on a disk device object, if the mode of the caller is kernel mode.
old-location: storage\ioctl_disk_internal_clear_verify.htm
old-project: storage
ms.assetid: 72d3b112-a5d2-4b2d-8102-bd3dfba31500
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DETECTION_TYPE, DETECTION_TYPE
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
req.alt-api: IOCTL_DISK_INTERNAL_CLEAR_VERIFY
req.alt-loc: Ntdddisk.h
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
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_INTERNAL_CLEAR_VERIFY IOCTL



## -description

Allows a driver to clear the verify bit on a disk device object, if the mode of the caller is kernel mode.



Allows a driver to clear the verify bit on a disk device object, if the mode of the caller is kernel mode.



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
I/O Status block
The <b>Status</b> field is set to STATUS_SUCCESS. If the mode of the requester is not kernel mode, the requested operation is not performed, but STATUS_SUCCESS is still returned.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_internal_set_verify.md">IOCTL_DISK_INTERNAL_SET_VERIFY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_INTERNAL_CLEAR_VERIFY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

