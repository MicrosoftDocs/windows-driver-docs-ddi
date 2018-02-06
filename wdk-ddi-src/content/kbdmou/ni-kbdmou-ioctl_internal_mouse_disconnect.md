---
UID: NI:kbdmou.IOCTL_INTERNAL_MOUSE_DISCONNECT
title: IOCTL_INTERNAL_MOUSE_DISCONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_MOUSE_DISCONNECT request is completed by Moufiltr with an error status of STATUS_NOT_IMPLEMENTED.
old-location: hid\ioctl_internal_mouse_disconnect.htm
old-project: hid
ms.assetid: e62c61e7-ef64-4939-ad24-686d137b6319
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.ioctl_internal_mouse_disconnect, IOCTL_INTERNAL_MOUSE_DISCONNECT control code [Human Input Devices], IOCTL_INTERNAL_MOUSE_DISCONNECT, kbdmou/IOCTL_INTERNAL_MOUSE_DISCONNECT, mfilref_11062207-6bb0-4a84-aaee-c3c086812b90.xml
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
-	kbdmou.h
apiname:
-	IOCTL_INTERNAL_MOUSE_DISCONNECT
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_SessionStatistics, MSiSCSI_SessionStatistics"
---

# IOCTL_INTERNAL_MOUSE_DISCONNECT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The IOCTL_INTERNAL_MOUSE_DISCONNECT request is completed by Moufiltr with an error status of STATUS_NOT_IMPLEMENTED. (Note that a Plug and Play mouse device can be added or removed by the Plug and Play manager.)


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

The <b>Status</b> member is set to STATUS_NOT_IMPLEMENTED.


## -see-also

<a href="..\kbdmou\ni-kbdmou-ioctl_internal_mouse_connect.md">IOCTL_INTERNAL_MOUSE_CONNECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_MOUSE_DISCONNECT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

