---
UID: NI:lamp.IOCTL_LAMP_SET_MODE
title: IOCTL_LAMP_SET_MODE (lamp.h)
description: The IOCTL_LAMP_SET_MODE control code sets the mode in which the lamp operates.
old-location: stream\ioctl_lamp_set_mode.htm
tech.root: stream
ms.assetid: 188F8AC8-BB1A-43C1-9933-5E03F954C2C0
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_SET_MODE, IOCTL_LAMP_SET_MODE control, IOCTL_LAMP_SET_MODE control code [Streaming Media Devices], lamp/IOCTL_LAMP_SET_MODE, stream.ioctl_lamp_set_mode
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- lamp.h
api_name:
- IOCTL_LAMP_SET_MODE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_SET_MODE IOCTL


## -description


The <b>IOCTL_LAMP_SET_MODE</b> 
   control code sets the mode in which the lamp operates.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_SET_MODE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0003, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

## -ioctlparameters




### -input-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a buffer of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn937009">LAMP_MODE</a>.


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937009">LAMP_MODE</a>.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.


