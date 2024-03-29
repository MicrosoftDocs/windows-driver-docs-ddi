---
UID: NI:hidport.IOCTL_HID_WRITE_REPORT
title: IOCTL_HID_WRITE_REPORT (hidport.h)
description: The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.
old-location: hid\ioctl_hid_write_report.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["IOCTL_HID_WRITE_REPORT IOCTL"]
ms.keywords: IOCTL_HID_WRITE_REPORT, IOCTL_HID_WRITE_REPORT control, IOCTL_HID_WRITE_REPORT control code [Human Input Devices], hid.ioctl_hid_write_report, hidioreq_0b1eb214-55b0-4659-bdf7-866cf03a7be6.xml, hidport/IOCTL_HID_WRITE_REPORT
req.header: hidport.h
req.include-header: Hidport.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_HID_WRITE_REPORT
 - hidport/IOCTL_HID_WRITE_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidport.h
api_name:
 - IOCTL_HID_WRITE_REPORT
---

# IOCTL_HID_WRITE_REPORT IOCTL


## -description

The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.

For general information about HIDClass devices, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

<b>Irp->UserBuffer </b> points to a <a href="/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a> structure the contains the parameters and report to be transmitted to the device. The following members are used:

### -input-buffer-length

The size of a <a href="/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a> structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred to the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IOCTL to carry out the I/O to their device, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.

## -ReportID

Specifies the report identifier, for this collection, of the report data to be written to the device.

## -reportBuffer

A pointer to a resident buffer containing the data to be sent to the device.

## -reportBufferLen

Specifies the length of the buffer provided at <b>reportBuffer</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getfeature">HidD_GetFeature</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport">HidD_GetInputReport</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setfeature">HidD_SetFeature</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setoutputreport">HidD_SetOutputReport</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_hid_read_report">IOCTL_HID_READ_REPORT</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a>
