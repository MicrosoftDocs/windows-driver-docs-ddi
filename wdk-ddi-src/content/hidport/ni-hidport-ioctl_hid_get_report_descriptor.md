---
UID: NI:hidport.IOCTL_HID_GET_REPORT_DESCRIPTOR
title: IOCTL_HID_GET_REPORT_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_HID_GET_REPORT_DESCRIPTOR request obtains the report descriptor for a HIDClass device.
old-location: hid\ioctl_hid_get_report_descriptor.htm
old-project: hid
ms.assetid: 7f0e6295-9c96-4167-8414-6f7b7b171f37
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_GET_REPORT_DESCRIPTOR, IOCTL_HID_GET_REPORT_DESCRIPTOR control code [Human Input Devices], hid.ioctl_hid_get_report_descriptor, hidioreq_01b638bd-f2d5-4acc-8527-9fd98bde8144.xml, hidport/IOCTL_HID_GET_REPORT_DESCRIPTOR
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hidport.h
apiname:
-	IOCTL_HID_GET_REPORT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_HID_GET_REPORT_DESCRIPTOR IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The IOCTL_HID_GET_REPORT_DESCRIPTOR request obtains the report descriptor for a HIDClass device.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the length, in bytes, of the locked-down buffer at <b>Irp-&gt;UserBuffer</b>.


### -input-buffer-length

The size of <b>OutputBufferLength</b>.


### -output-buffer

The HID minidriver fills the buffer at <b>Irp-&gt;UserBuffer</b> with the report descriptor.


### -output-buffer-length

The size of the report descriptor.


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

<a href="..\hidport\ni-hidport-ioctl_hid_get_device_descriptor.md">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a>



<a href="..\hidclass\ni-hidclass-ioctl_get_physical_descriptor.md">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_REPORT_DESCRIPTOR control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

