---
UID: NI:lamp.IOCTL_LAMP_GET_EMITTING_LIGHT
title: IOCTL_LAMP_GET_EMITTING_LIGHT
author: windows-driver-content
description: The IOCTL_LAMP_GET_EMITTING_LIGHT control code queries if the lamp is turned on.
old-location: stream\ioctl_lamp_get_emitting_light.htm
old-project: stream
ms.assetid: 82BBD72D-9F65-442F-8B25-E80A2160C5A2
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_LAMP_GET_EMITTING_LIGHT, IOCTL_LAMP_GET_EMITTING_LIGHT control, IOCTL_LAMP_GET_EMITTING_LIGHT control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_EMITTING_LIGHT, stream.ioctl_lamp_get_emitting_light
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
-	lamp.h
api_name:
-	IOCTL_LAMP_GET_EMITTING_LIGHT
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_EMITTING_LIGHT IOCTL


## -description


The <b>IOCTL_LAMP_GET_EMITTING_LIGHT</b> 
   control code queries if the lamp is turned on.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_GET_EMITTING_LIGHT \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0008, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

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

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status. It will set <code>Irp-&gt;IoStatus.Information</code> to the number of bytes required to hold a <b>DWORD</b> value.


If the device has been acquired by a camera driver, the lamp driver should return a <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.

