---
UID: NI:usbprint.IOCTL_USBPRINT_VENDOR_SET_COMMAND
title: IOCTL_USBPRINT_VENDOR_SET_COMMAND (usbprint.h)
description: The IOCTL_USBPRINT_VENDOR_SET_COMMAND request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device.
old-location: print\ioctl_usbprint_vendor_set_command.htm
tech.root: print
ms.assetid: 3fbb3e5d-e7a3-4d76-9996-50375ed9fd03
ms.date: 04/20/2018
ms.keywords: IOCTL_USBPRINT_VENDOR_SET_COMMAND, IOCTL_USBPRINT_VENDOR_SET_COMMAND control, IOCTL_USBPRINT_VENDOR_SET_COMMAND control code [Print Devices], print.ioctl_usbprint_vendor_set_command, usbioctl_b3ea3ada-47c2-4acc-b08c-2d16e9d3ead1.xml, usbprint/IOCTL_USBPRINT_VENDOR_SET_COMMAND
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbprint.h
api_name:
- IOCTL_USBPRINT_VENDOR_SET_COMMAND
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USBPRINT_VENDOR_SET_COMMAND IOCTL


## -description


The <b>IOCTL_USBPRINT_VENDOR_SET_COMMAND</b> request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device. 



## -ioctlparameters




### -input-buffer

A pointer to a input buffer, an array of UCHAR elements. The meaning of each array element is shown in the following table.

<table>
<tr>
<th>Array Element</th>
<th>Contents</th>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[0]

</td>
<td>
Vendor request code

</td>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[1]

</td>
<td>
Vendor request value (most significant byte)

</td>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[2]

</td>
<td>
Vendor request value (least significant byte)

</td>
</tr>
<tr>
<td>
<i>lpInBuffer</i>[3], ...

</td>
<td>
Any additional data to be sent as part of the command

</td>
</tr>
</table>
 


### -input-buffer-length

The size of the input buffer, in bytes.


### -output-buffer

Not used in this operation; set this parameter to <b>NULL</b>.


### -output-buffer-length

Not used in this operation; set this parameter to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbprint/ni-usbprint-ioctl_usbprint_vendor_get_command">IOCTL_USBPRINT_VENDOR_GET_COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

