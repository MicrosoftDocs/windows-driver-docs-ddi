---
UID: NI:kbdmou.IOCTL_INTERNAL_MOUSE_DISCONNECT
title: IOCTL_INTERNAL_MOUSE_DISCONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_MOUSE_DISCONNECT request is completed by Moufiltr with an error status of STATUS_NOT_IMPLEMENTED.
old-location: hid\ioctl_internal_mouse_disconnect.htm
old-project: hid
ms.assetid: e62c61e7-ef64-4939-ad24-686d137b6319
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IOCTL_INTERNAL_MOUSE_DISCONNECT, IOCTL_INTERNAL_MOUSE_DISCONNECT control, IOCTL_INTERNAL_MOUSE_DISCONNECT control code [Human Input Devices], hid.ioctl_internal_mouse_disconnect, kbdmou/IOCTL_INTERNAL_MOUSE_DISCONNECT, mfilref_11062207-6bb0-4a84-aaee-c3c086812b90.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	kbdmou.h
api_name:
-	IOCTL_INTERNAL_MOUSE_DISCONNECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_MOUSE_DISCONNECT IOCTL


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541294">IOCTL_INTERNAL_MOUSE_CONNECT</a>
 

 

