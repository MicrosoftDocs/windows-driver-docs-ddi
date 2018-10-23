---
UID: NI:hidclass.IOCTL_HID_SET_FEATURE
title: IOCTL_HID_SET_FEATURE
author: windows-driver-content
description: The IOCTL_HID_SET_FEATURE request sends a feature report to a top-level collection.
old-location: hid\ioctl_hid_set_feature2.htm
tech.root: hid
ms.assetid: cbadc87a-b676-4df7-8116-b9692d93e345
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_SET_FEATURE, IOCTL_HID_SET_FEATURE control, IOCTL_HID_SET_FEATURE control code [Human Input Devices], hid.ioctl_hid_set_feature2, hidclass/IOCTL_HID_SET_FEATURE, hidioreq_def58360-8e73-49dd-ab90-33cf3b6a92de.xml
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
-	IOCTL_HID_SET_FEATURE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_SET_FEATURE IOCTL


## -description


The IOCTL_HID_SET_FEATURE request sends a feature report to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a requester-allocated input buffer that contains a HID class feature report.

The input buffer size, in bytes, must be large enough to hold the feature report -- excluding its report ID, if report IDs are used - plus one additional byte that specifies a nonzero report ID or zero.

The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> member points to the input buffer that contains a feature report. If the collection includes report IDs, the requester must set the first byte of the buffer to a nonzero report ID; otherwise the requester must set the first byte to zero. The feature report -- excluding its report ID, if report IDs are used - is located at ((PUCHAR)<i>ReportBuffer</i> + 1).

<b>Minidriver handling</b>

<b>Irp-&gt;UserBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure that the HID class driver uses to input the following members:




#### -ReportID

Specifies the report ID for a top-level collection .


#### -reportBuffer

Pointer to a requester-allocated input buffer that contains a feature report.


#### -reportBufferLen

Specifies the size, in bytes, of the input buffer.


### -input-buffer-length

The input buffer size, in bytes, must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

<b>Minidriver handling</b>

 The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539949">HID_XFER_PACKET</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


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
<b>Information</b> is set to the number of bytes transferred to the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>
HID minidrivers that call other drivers with this IOCTL to carry out the I/O, should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538910">HidD_GetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538945">HidD_GetInputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539684">HidD_SetFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539690">HidD_SetOutputReport</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541126">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541196">IOCTL_HID_SET_OUTPUT_REPORT</a>
 

 

