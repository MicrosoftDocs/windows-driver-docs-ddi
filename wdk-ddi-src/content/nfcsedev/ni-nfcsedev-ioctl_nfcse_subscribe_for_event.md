---
UID: NI:nfcsedev.IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT
title: IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT
author: windows-driver-content
description: The IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT control code is issued by a client to subscribe to a specific event.
old-location: nfpdrivers\ioctl_nfcse_subscribe_for_event.htm
old-project: nfpdrivers
ms.assetid: 3A184392-A68C-4AFC-AE9F-36247153ADD2
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT
req.alt-loc: nfcsedev.h
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
req.typenames: *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
---

# IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT IOCTL



## -description
The <b>IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT</b> 
   control code is issued by a client to subscribe to a specific event. 



## -ioctlparameters

### -input-buffer

<a href="..\nfcsedev\ns-nfcsedev-_secure_element_event_subscription_info.md"> SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO</a> structure.



### -input-buffer-length

<text></text>

### -output-buffer
None


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks
The following are requirements that the driver must adhere to.<ul>
<li>This IOCTL must be called on a handle with a <b>SEEvents</b> file name; otherwise, the driver returns STATUS_INVALID_DEVICE_STATE.</li>
<li><b>GUID_NULL</b> can be specified by the client as a wild card to subscribe for a specific event from all enumerated secure elements.</li>
</ul>
</p>