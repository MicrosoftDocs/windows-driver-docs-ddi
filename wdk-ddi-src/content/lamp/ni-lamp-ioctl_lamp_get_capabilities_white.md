---
UID: NI:lamp.IOCTL_LAMP_GET_CAPABILITIES_WHITE
title: IOCTL_LAMP_GET_CAPABILITIES_WHITE
author: windows-driver-content
description: The IOCTL_LAMP_GET_CAPABILITIES_WHITE control code queries the capabilities of the lamp when the device is configured to emit white light.
old-location: stream\ioctl_lamp_get_capabilities_white.htm
old-project: stream
ms.assetid: F4A7CF9A-023F-42FC-A40C-E95964EC5392
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_LAMP_GET_CAPABILITIES_WHITE, IOCTL_LAMP_GET_CAPABILITIES_WHITE control, IOCTL_LAMP_GET_CAPABILITIES_WHITE control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_CAPABILITIES_WHITE, stream.ioctl_lamp_get_capabilities_white
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
-	IOCTL_LAMP_GET_CAPABILITIES_WHITE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_CAPABILITIES_WHITE IOCTL


## -description


The <b>IOCTL_LAMP_GET_CAPABILITIES_WHITE</b> 
   control code queries the capabilities of the lamp when the device is configured to emit white light.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_GET_CAPABILITIES_WHITE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0000, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

## -ioctlparameters




### -input-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a buffer of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn937002">LAMP_CAPABILITIES_WHITE</a>.


### -input-buffer-length

Length of the buffer.


### -output-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> is filled with all capabilities supported by the lamp hardware.


### -output-buffer-length

<code>IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength</code> is the length of the buffer (in bytes) passed in the <code>Irp-&gt;AssociatedIrp.SystemBuffer</code> field.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status. It will set <code>Irp-&gt;IoStatus.Information</code> to the number of bytes required to hold the buffer.


## -remarks



By requirement, a lamp whose driver supports the <b>GUID_DEVINTERFACE_LAMP</b> interface is required to support emitting white light.

The payload of this IOCTL is a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937002">LAMP_CAPABILITIES_WHITE</a> structure.

The <b>IsLightIntensityAdjustable</b> field indicates whether the luminance level can be programmed. If this field evaluates to <b>FALSE</b>, it means that the underlying device only supports the on/off switch and the light intensity cannot be adjusted.



