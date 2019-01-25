---
UID: NI:lamp.IOCTL_LAMP_SET_INTENSITY_WHITE
title: IOCTL_LAMP_SET_INTENSITY_WHITE (lamp.h)
description: The IOCTL_LAMP_SET_INTENSITY_WHITE control code sets the lamp to the specified light intensity.
old-location: stream\ioctl_lamp_set_intensity_white.htm
tech.root: stream
ms.assetid: 78541C4C-AA0E-4C1F-A7B5-E2A39DF5E2CE
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_SET_INTENSITY_WHITE, IOCTL_LAMP_SET_INTENSITY_WHITE control, IOCTL_LAMP_SET_INTENSITY_WHITE control code [Streaming Media Devices], lamp/IOCTL_LAMP_SET_INTENSITY_WHITE, stream.ioctl_lamp_set_intensity_white
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
-	IOCTL_LAMP_SET_INTENSITY_WHITE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_SET_INTENSITY_WHITE IOCTL


## -description


The <b>IOCTL_LAMP_SET_INTENSITY_WHITE</b> 
   control code sets the lamp to the specified light intensity.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_SET_INTENSITY_WHITE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0005, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

## -ioctlparameters




### -input-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937006">LAMP_INTENSITY_WHITE</a> structure.


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937006">LAMP_INTENSITY_WHITE</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a  <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.

