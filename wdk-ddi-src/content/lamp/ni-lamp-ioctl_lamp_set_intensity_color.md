---
UID: NI:lamp.IOCTL_LAMP_SET_INTENSITY_COLOR
title: IOCTL_LAMP_SET_INTENSITY_COLOR
author: windows-driver-content
description: The IOCTL_LAMP_SET_INTENSITY_COLOR control code sets the lamp to the specified light intensity.
old-location: stream\ioctl_lamp_set_intensity_color.htm
old-project: stream
ms.assetid: AD531C16-0E24-4CDE-B188-981260CF8F49
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_LAMP_SET_INTENSITY_COLOR, IOCTL_LAMP_SET_INTENSITY_COLOR control code [Streaming Media Devices], lamp/IOCTL_LAMP_SET_INTENSITY_COLOR, stream.ioctl_lamp_set_intensity_color
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
-	IOCTL_LAMP_SET_INTENSITY_COLOR
product: Windows
targetos: Windows
req.typenames: LAMP_MODE
---

# IOCTL_LAMP_SET_INTENSITY_COLOR IOCTL


## -description


The <b>IOCTL_LAMP_SET_INTENSITY_COLOR</b> 
   control code sets the lamp to the specified light intensity.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_SET_INTENSITY_COLOR \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0007, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

## -ioctlparameters




### -input-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a <a href="..\lamp\ns-lamp-lamp_intensity_color.md">LAMP_INTENSITY_COLOR</a> structure.


### -input-buffer-length

Length of a <a href="..\lamp\ns-lamp-lamp_intensity_color.md">LAMP_INTENSITY_COLOR</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.

