---
UID: NI:acpiioct.IOCTL_ACPI_GET_DEVICE_INFORMATION
title: IOCTL_ACPI_GET_DEVICE_INFORMATION
author: windows-driver-content
description: A driver for a device can use the IOCTL_ACPI_GET_DEVICE_INFORMATION device control request to obtain fine-grained identification information about its device.
old-location: acpi\ioctl_acpi_get_device_information.htm
old-project: acpi
ms.assetid: 08C27EC1-0948-4E8F-A391-01FE2C1A34DB
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_ACPI_GET_DEVICE_INFORMATION, IOCTL_ACPI_GET_DEVICE_INFORMATION control code [ACPI Devices], acpi.ioctl_acpi_get_device_information, acpiioct/IOCTL_ACPI_GET_DEVICE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8 and later versions of Windows.
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
-	Acpiioct.h
api_name:
-	IOCTL_ACPI_GET_DEVICE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
---

# IOCTL_ACPI_GET_DEVICE_INFORMATION IOCTL


## -description


A driver for a device can use the IOCTL_ACPI_GET_DEVICE_INFORMATION device control request to obtain fine-grained identification information about its device. This IOCTL is typically used by drivers that support multiple versions or revisions of a device, and need to examine the component parts that make up the device's HW ID string to identify the exact device. The driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a> and pass the following input and output parameters to build this request.


## -ioctlparameters




### -input-buffer

Set the <b>IoBuildDeviceIoControlRequest</b> input parameters as follows:

<ul>
<li>
<i>IoControlCode</i> is set to IOCTL_ACPI_GET_DEVICE_INFORMATION.

</li>
<li>
<i>DeviceObject</i> is set to a pointer to the physical device object (PDO) of the device.

</li>
<li>
<i>InputBuffer</i> is set to a pointer to an input buffer structure that depends on the type of input arguments to be passed to the control method. For more information about the type of input arguments that this IOCTL supports, see the Remarks section later in this topic.

</li>
<li>
<i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.

</li>
<li>
<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.

</li>
<li>
<i>InternalDeviceIoControl</i> is set to <b>FALSE</b>.

</li>
<li>
<i>Event</i> is set to <b>NULL</b>.

</li>
</ul>

### -input-buffer-length

<i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.


### -output-buffer

Set the <b>IoBuildDeviceIoControlRequest</b> output parameters as follows:

<ul>
<li>
<i>OutputBuffer</i> supplies a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450789">ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER</a> structure that contains the output arguments from the control method.

</li>
<li>
<i>IoStatusBlock</i> is set to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure.

</li>
</ul>

### -output-buffer-length

<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the output buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain all the output arguments from the control method, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW, and <i>OutputBuffer</i>-&gt;<b>Length</b> is set to the required length of the output buffer.

If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.


## -remarks



A driver for a device can use IOCTL_ACPI_GET_DEVICE_INFORMATION to obtain fine-grained identification information about its device. This IOCTL is typically used with drivers that support multiple hardware versions or revisions of a device, and need to examine the component parts that make up the device's HW ID string to identify the exact device. For example, a driver may support different revisions of the same device, in which some aspect of the programing interface or the device's behavior is different. The driver can identify exactly which revision it is running on.

The output arguments from the request are returned in the variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/hh450789">ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER</a> structure that is supplied by the <i>OutBuffer</i> pointer. The ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER includes an array of variable-length arrays, each of which returns an output argument representing the sub-system ID string, vendor ID string, and instance ID string, respectively.

IOCTL_ACPI_GET_DEVICE_INFORMATION can be used only at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450789">ACPI_DEVICE_INFORMATION_OUTPUT_BUFFER</a>
 

 

