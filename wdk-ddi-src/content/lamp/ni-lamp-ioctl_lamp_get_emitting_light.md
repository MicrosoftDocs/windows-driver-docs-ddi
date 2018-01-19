---
UID: NI:lamp.IOCTL_LAMP_GET_EMITTING_LIGHT
title: IOCTL_LAMP_GET_EMITTING_LIGHT
author: windows-driver-content
description: The IOCTL_LAMP_GET_EMITTING_LIGHT control code queries if the lamp is turned on.
old-location: stream\ioctl_lamp_get_emitting_light.htm
old-project: stream
ms.assetid: 82BBD72D-9F65-442F-8B25-E80A2160C5A2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: LAMP_MODE, LAMP_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: lamp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_LAMP_GET_EMITTING_LIGHT
req.alt-loc: lamp.h
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
req.typenames: LAMP_MODE
---

# IOCTL_LAMP_GET_EMITTING_LIGHT IOCTL



## -description
The <b>IOCTL_LAMP_GET_EMITTING_LIGHT</b> 
   control code queries if the lamp is turned on.



## -syntax

````
#define IOCTL_LAMP_GET_EMITTING_LIGHT \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0008, METHOD_BUFFERED, FILE_ANY_ACCESS)
````


## -ioctlparameters

### -input-buffer
<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a buffer of type <b>BOOLEAN</b>.


### -input-buffer-length
Length of a <b>BOOLEAN</b>.


### -output-buffer
<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> contains the lamp state; <b>TRUE</b> if the lamp is turned on and emitting light; <b>FALSE</b> otherwise.


### -output-buffer-length
<code>IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength</code> is the length of the buffer in bytes passed in the <code>Irp-&gt;AssociatedIrp.SystemBuffer</code> field.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status. It will set <code>Irp-&gt;IoStatus.Information</code> to the number of bytes required to hold a <b>DWORD</b> value.


If the device has been acquired by a camera driver, the lamp driver should return a <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.


## -remarks
