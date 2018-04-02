---
UID: NI:hidport.IOCTL_HID_WRITE_REPORT
title: IOCTL_HID_WRITE_REPORT
author: windows-driver-content
description: The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.
old-location: hid\ioctl_hid_write_report.htm
old-project: hid
ms.assetid: 30b56c97-f135-4603-a5f0-3ed2105aae59
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_WRITE_REPORT, IOCTL_HID_WRITE_REPORT control code [Human Input Devices], hid.ioctl_hid_write_report, hidioreq_0b1eb214-55b0-4659-bdf7-866cf03a7be6.xml, hidport/IOCTL_HID_WRITE_REPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hidport.h
api_name:
-	IOCTL_HID_WRITE_REPORT
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_HID_WRITE_REPORT IOCTL


## -description


The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Irp-&gt;UserBuffer </b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure the contains the parameters and report to be transmitted to the device. The following members are used:




#### -ReportID

Specifies the report identifier, for this collection, of the report data to be written to the device.


#### -reportBuffer

A pointer to a resident buffer containing the data to be sent to the device.


#### -reportBufferLen

Specifies the length of the buffer provided at <b>reportBuffer</b>.


### -input-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block


       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred to the device.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541100">IOCTL_HID_GET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541172">IOCTL_HID_READ_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

