---
UID: NI:hidclass.IOCTL_HID_GET_FEATURE
title: IOCTL_HID_GET_FEATURE
author: windows-driver-content
description: The IOCTL_HID_GET_FEATURE request obtains a feature report from a HIDClass device.
old-location: hid\ioctl_hid_get_feature.htm
old-project: hid
ms.assetid: c77b4899-b76a-486c-aecd-7e052a1d9256
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_GET_FEATURE, IOCTL_HID_GET_FEATURE control code [Human Input Devices], hid.ioctl_hid_get_feature, hidclass/IOCTL_HID_GET_FEATURE, hidioreq_2933a93c-ff74-41b8-9b0a-d1a8ae32b1cb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
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
-	hidclass.h
api_name:
-	IOCTL_HID_GET_FEATURE
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_FEATURE IOCTL


## -description


The IOCTL_HID_GET_FEATURE request obtains a feature report from a HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Irp-&gt;UserBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure that the HID class driver uses to input the following members:




#### -ReportID

Specifies a report ID associated with a top-level collection.


#### -reportBuffer

Points to a requester-allocated output buffer that a HID minidriver uses to return a feature report.


#### -reportBufferLen

Specifies the size, in bytes, of the output buffer.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure.


### -output-buffer

((PHID_XFER_PACKET)(<b>Irp-&gt;UserBuffer</b>))-&gt;<b>reportBuffer</b> points to the requester-allocated output buffer that the HID minidriver uses to return a feature report.


### -output-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IOCTL to carry out the I/O to their device, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538910">HidD_GetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538945">HidD_GetInputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539684">HidD_SetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539690">HidD_SetOutputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541172">IOCTL_HID_READ_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439646">IOCTL_HID_WRITE_REPORT</a>
 

 

