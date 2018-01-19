---
UID: NI:kbdmou.IOCTL_INTERNAL_KEYBOARD_DISCONNECT
title: IOCTL_INTERNAL_KEYBOARD_DISCONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_KEYBOARD_DISCONNECT request is completed with a status of STATUS_NOT_IMPLEMENTED. Note that a Plug and Play keyboard can be added or removed by the Plug and Play manager.
old-location: hid\ioctl_internal_keyboard_disconnect.htm
old-project: hid
ms.assetid: ec1c2267-b92c-4d4c-86fa-f2b3ccb6aa40
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _MSiSCSI_SessionStatistics, MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: kbdmou.h
req.include-header: Kbdmou.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_KEYBOARD_DISCONNECT
req.alt-loc: kbdmou.h
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
req.typenames: MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics
---

# IOCTL_INTERNAL_KEYBOARD_DISCONNECT IOCTL



## -description

The IOCTL_INTERNAL_KEYBOARD_DISCONNECT request is completed with a status of STATUS_NOT_IMPLEMENTED. Note that a Plug and Play keyboard can be added or removed by the Plug and Play manager.



The IOCTL_INTERNAL_KEYBOARD_DISCONNECT request is completed with a status of STATUS_NOT_IMPLEMENTED. Note that a Plug and Play keyboard can be added or removed by the Plug and Play manager.



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
I/O Status block
The <b>Status</b> member is set to STATUS_NOT_IMPLEMENTED.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_KEYBOARD_DISCONNECT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

