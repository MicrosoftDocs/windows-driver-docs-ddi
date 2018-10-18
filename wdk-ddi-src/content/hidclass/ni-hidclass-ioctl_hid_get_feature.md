---
UID: NI:hidclass.IOCTL_HID_GET_FEATURE
title: IOCTL_HID_GET_FEATURE
author: windows-driver-content
description: The IOCTL_HID_GET_FEATURE request returns a feature report associated with a top-level collection.
old-location: hid\ioctl_hid_get_feature2.htm
tech.root: hid
ms.assetid: 86ae1bd2-8c19-47e4-a551-f039d2eb8f47
ms.date: 4/30/2018
ms.keywords: IOCTL_HID_GET_FEATURE, IOCTL_HID_GET_FEATURE control, IOCTL_HID_GET_FEATURE control code [Human Input Devices], hid.ioctl_hid_get_feature2, hidclass/IOCTL_HID_GET_FEATURE, hidioreq_3257c7bb-bf6e-4731-afb1-82cb6b0f28a5.xml
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
req.typenames: 
---

# IOCTL_HID_GET_FEATURE IOCTL


## -description


The IOCTL_HID_GET_FEATURE request returns a feature report associated with a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. The HID class driver uses this buffer to return a feature report. 

If the collection includes report IDs, the requester must set the first byte of the output buffer to a nonzero report ID. Otherwise, the requester must set the first byte of the output buffer to zero.

<b>Minidriver handling</b>

<b>Irp-&gt;UserBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure that the HID class driver uses to input the following members:




#### -ReportID

Specifies a report ID associated with a top-level collection.


#### -reportBuffer

Points to a requester-allocated output buffer that a HID minidriver uses to return a feature report.


#### -reportBufferLen

Specifies the size, in bytes, of the output buffer.


### -input-buffer-length

The buffer size, in bytes, must be large enough to hold the feature report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

<b>Minidriver handling</b>

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure.


### -output-buffer

The <b>Irp-&gt;MdlAddress</b> member points to the requester-allocated output buffer that the HID class driver uses to return the feature report. The first byte of the buffer, which the requester uses to input a report ID or zero, is unchanged. The feature report, excluding its report ID, if report IDs are used, is returned at ((PUCHAR)<b>Irp</b>-&gt;<b>MdlAddress</b> + 1).

<b>Minidriver handling</b>

((PHID_XFER_PACKET)(<b>Irp-&gt;UserBuffer</b>))-&gt;<b>reportBuffer</b> points to the requester-allocated output buffer that the HID minidriver uses to return a feature report.


### -output-buffer-length

The length of the buffer that contains the report.

<b>Minidriver handling</b>

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure.




### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
<b>Minidriver handling</b>

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538910">HidD_GetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538945">HidD_GetInputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539684">HidD_SetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539690">HidD_SetOutputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

