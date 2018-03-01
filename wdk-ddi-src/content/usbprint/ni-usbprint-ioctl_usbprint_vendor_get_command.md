---
UID: NI:usbprint.IOCTL_USBPRINT_VENDOR_GET_COMMAND
title: IOCTL_USBPRINT_VENDOR_GET_COMMAND
author: windows-driver-content
description: The IOCTL_USBPRINT_VENDOR_GET_COMMAND request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device.
old-location: print\ioctl_usbprint_vendor_get_command.htm
old-project: print
ms.assetid: d4e0220b-2efb-4a24-b80a-23225b06dc66
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_USBPRINT_VENDOR_GET_COMMAND, IOCTL_USBPRINT_VENDOR_GET_COMMAND control code [Print Devices], print.ioctl_usbprint_vendor_get_command, usbioctl_edd39494-a6bb-4e28-a059-7c7884626105.xml, usbprint/IOCTL_USBPRINT_VENDOR_GET_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbprint.h
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
-	usbprint.h
api_name:
-	IOCTL_USBPRINT_VENDOR_GET_COMMAND
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# IOCTL_USBPRINT_VENDOR_GET_COMMAND IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_USBPRINT_VENDOR_GET_COMMAND</b> request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device.


## -ioctlparameters




### -input-buffer

A pointer to a buffer, an array of UCHAR elements. The meaning of each array element is shown in the following table.

<table>
<tr>
<th>Array Element</th>
<th>Contents</th>
</tr>
<tr>
<td>
<i>lpOutBuffer</i>[0]

</td>
<td>
Vendor request code 

</td>
</tr>
<tr>
<td>
<i>lpOutBuffer</i>[1]

</td>
<td>
Vendor request value (most significant byte)

</td>
</tr>
<tr>
<td>
<i>lpOutBuffer</i>[2]

</td>
<td>
Vendor request value (least significant byte)

</td>
</tr>
</table>
 


### -input-buffer-length

The size of the input buffer, in bytes.


### -output-buffer

The output buffer, which is interpreted as an array of bytes. 


### -output-buffer-length

The size of the output buffer, in bytes.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\usbprint\ni-usbprint-ioctl_usbprint_vendor_set_command.md">IOCTL_USBPRINT_VENDOR_SET_COMMAND</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IOCTL_USBPRINT_VENDOR_GET_COMMAND control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

