---
UID: NI:hidclass.IOCTL_HID_GET_INPUT_REPORT
title: IOCTL_HID_GET_INPUT_REPORT
author: windows-driver-content
description: The IOCTL_HID_GET_INPUT_REPORT request obtains an input report from a top-level collection.
old-location: hid\ioctl_hid_get_input_report2.htm
tech.root: hid
ms.assetid: 968a3498-efd4-4097-a7ac-17e47809a7c9
ms.date: 4/30/2018
ms.keywords: IOCTL_HID_GET_INPUT_REPORT, IOCTL_HID_GET_INPUT_REPORT control, IOCTL_HID_GET_INPUT_REPORT control code [Human Input Devices], hid.ioctl_hid_get_input_report2, hidclass/IOCTL_HID_GET_INPUT_REPORT, hidioreq_d9b80227-8a48-439e-80de-3b0e722e3576.xml
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
-	IOCTL_HID_GET_INPUT_REPORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_INPUT_REPORT IOCTL


## -description


The IOCTL_HID_GET_INPUT_REPORT request obtains an input report from a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. The HID class driver uses this buffer to return an input report. 

If the collection includes report IDs, the requester must set the first byte of the output buffer to a nonzero report ID. Otherwise, the requester must set the first byte of the output buffer to zero.

<b>Minidriver handling</b>

<b>Irp-&gt;UserBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure that the HID class driver uses to input the following members:




#### -ReportID

Specifies a report ID associated with a top-level collection.


#### -reportBuffer

Points to a requester-allocated output buffer that a HID minidriver uses to return an input report.


#### -reportBufferLen

Specifies the size, in bytes, of the output buffer.


### -input-buffer-length

The buffer size, in bytes, must be large enough to hold the input report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.


### -output-buffer

The <b>Irp-&gt;MdlAddress</b> member points to the requester-allocated output buffer that the HID class driver uses to return the input report. The first byte of the buffer, which the requester uses to input a report ID or zero, is unchanged. The input report -- excluding its report ID, if report IDs are used -- is returned at ((PUCHAR)<b>Irp</b>-&gt;<b>MdlAddress</b> + 1).

<b>Minidriver handling</b>

((PHID_XFER_PACKET)(<b>Irp-&gt;UserBuffer</b>))-&gt;<b>reportBuffer</b> points to the requester-allocated output buffer that the HID minidriver uses to return the input report.


### -output-buffer-length

The size of the input report.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to zero.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541100">IOCTL_HID_GET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

