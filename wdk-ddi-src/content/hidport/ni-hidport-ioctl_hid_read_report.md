---
UID: NI:hidport.IOCTL_HID_READ_REPORT
title: IOCTL_HID_READ_REPORT (hidport.h)
description: The IOCTL_HID_READ_REPORT request transfers an input report from a HIDClass device into the HID class driver's buffer.
old-location: hid\ioctl_hid_read_report.htm
tech.root: hid
ms.assetid: 83a7cf49-6879-4e91-b398-d97d4b69e5b1
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_READ_REPORT, IOCTL_HID_READ_REPORT control, IOCTL_HID_READ_REPORT control code [Human Input Devices], hid.ioctl_hid_read_report, hidioreq_e75980f5-3db7-4e29-b25a-9d3c3260d0f6.xml, hidport/IOCTL_HID_READ_REPORT
ms.topic: ioctl
f1_keywords:
 - "hidport/IOCTL_HID_READ_REPORT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hidport.h
api_name:
- IOCTL_HID_READ_REPORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_READ_REPORT IOCTL


## -description


The IOCTL_HID_READ_REPORT request transfers an input report from a HIDClass device into the HID class driver's buffer.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> contains the size of the buffer provided at <b>Irp->UserBuffer</b>.


### -input-buffer-length

The size of <b>OutputBufferLength</b>


### -output-buffer


       HID minidriver fills the system-resident buffer pointed to by <b>Irp->UserBuffer</b> with the report data retrieved from the device.


### -output-buffer-length

The size of the <b>UserBuffer</b>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -remarks



IOCTL_HID_READ_REPORT  is typically used for continuously completing input reports that are sent by the device. This IOCTL is sent down by the HID class driver (HIDCLASS) in ping-pong fashion. In other words, as soon as a request is fulfilled (completed), another one can be sent down to the device, allowing for continuous reporting of data. This is an “asynchronous” mechanism, so for example, the device can use it to send  data up to the host, regarding  changes in state as those changes occur.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getfeature">HidD_GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getinputreport">HidD_GetInputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_setfeature">HidD_SetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_setoutputreport">HidD_SetOutputReport</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a>



<a href="https://docs.microsoft.com/previous-versions/hh439646(v=vs.85)">IOCTL_HID_WRITE_REPORT</a>
 

 

