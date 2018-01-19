---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_STATUS
title: IOCTL_CHANGER_GET_STATUS
author: windows-driver-content
description: Returns the current status of the device.
old-location: storage\ioctl_changer_get_status.htm
old-project: storage
ms.assetid: 88f1a248-0beb-4c7c-b68d-6ce145bf5ca7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _ELEMENT_TYPE, *PELEMENT_TYPE, ELEMENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_CHANGER_GET_STATUS
req.alt-loc: Ntddchgr.h
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
req.typenames: *PELEMENT_TYPE, ELEMENT_TYPE
---

# IOCTL_CHANGER_GET_STATUS IOCTL



## -description
Returns the current status of the device.



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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES. 


## -remarks
