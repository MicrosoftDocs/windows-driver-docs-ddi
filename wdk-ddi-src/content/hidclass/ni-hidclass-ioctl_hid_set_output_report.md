---
UID: NI:hidclass.IOCTL_HID_SET_OUTPUT_REPORT
title: IOCTL_HID_SET_OUTPUT_REPORT (hidclass.h)
description: The IOCTL_HID_SET_OUTPUT_REPORT request sends an output report to a top-level collection.
old-location: hid\ioctl_hid_set_output_report.htm
tech.root: hid
ms.assetid: f5c0f3a7-5d90-4a95-9ba0-01aea98d8c79
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_SET_OUTPUT_REPORT, IOCTL_HID_SET_OUTPUT_REPORT control, IOCTL_HID_SET_OUTPUT_REPORT control code [Human Input Devices], hid.ioctl_hid_set_output_report, hidclass/IOCTL_HID_SET_OUTPUT_REPORT, hidioreq_1b4d06b6-4e28-4465-8b88-356d70bf1dee.xml
ms.topic: ioctl
f1_keywords:
 - "hidclass/IOCTL_HID_SET_OUTPUT_REPORT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hidclass.h
api_name:
- IOCTL_HID_SET_OUTPUT_REPORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_SET_OUTPUT_REPORT IOCTL


## -description


The IOCTL_HID_SET_OUTPUT_REPORT request sends an output report to a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a requester-allocated input buffer that contains a HID class output report.

The input buffer size, in bytes, must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

The <b>Irp->AssociatedIrp.SystemBuffer</b> member points to the input buffer that contains an output report. If the collection includes report IDs, the requester must set the first byte of the buffer to a nonzero report ID. Otherwise, the requester must set the first byte to zero. The output report -- excluding its report ID, if report IDs are used -- is located at ((PUCHAR)<i>ReportBuffer</i> + 1).

<b>Minidriver handling</b>

<b>Irp->UserBuffer</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a> structure that the HID class driver uses to input the following members:




#### -ReportID

Specifies the report ID for a top-level collection.


#### -reportBuffer

Pointer to a requester-allocated input buffer that contains an output report.


#### -reportBufferLen

Specifies the size, in bytes, of the output buffer.


### -input-buffer-length

The input buffer size, in bytes, must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

<b>Minidriver handling</b>

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to zero. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
<b>Minidriver handling</b>


       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred to the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IOCTL to carry out the I/O should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getfeature">HidD_GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getinputreport">HidD_GetInputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_setfeature">HidD_SetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_setoutputreport">HidD_SetOutputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>
 

 

