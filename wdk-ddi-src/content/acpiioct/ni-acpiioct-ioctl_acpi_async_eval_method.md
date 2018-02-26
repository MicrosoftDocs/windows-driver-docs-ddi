---
UID: NI:acpiioct.IOCTL_ACPI_ASYNC_EVAL_METHOD
title: IOCTL_ACPI_ASYNC_EVAL_METHOD
author: windows-driver-content
description: A driver for a device can use the IOCTL_ACPI_ASYNC_EVAL_METHOD device control request to asynchronously evaluate an ACPI control method that is supported by the device.
old-location: acpi\ioctl_acpi_async_eval_method.htm
old-project: acpi
ms.assetid: 43dcbd78-97c6-469e-9f66-f50959dc60e2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_ACPI_ASYNC_EVAL_METHOD, IOCTL_ACPI_ASYNC_EVAL_METHOD control code [ACPI Devices], acpi-meth-eval-ref_9de8fe00-63ec-41e3-bb6b-9fd14d1a788f.xml, acpi.ioctl_acpi_async_eval_method, acpiioct/IOCTL_ACPI_ASYNC_EVAL_METHOD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
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
-	Acpiioct.h
apiname:
-	IOCTL_ACPI_ASYNC_EVAL_METHOD
product: Windows
targetos: Windows
req.typenames: UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
---

# IOCTL_ACPI_ASYNC_EVAL_METHOD IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


A driver for a device can use the IOCTL_ACPI_ASYNC_EVAL_METHOD device control request to asynchronously evaluate an ACPI control method that is supported by the device. The driver should call <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> and pass the following input and output parameters to build this request. 


## -ioctlparameters




### -input-buffer

Set the <b>IoBuildDeviceIoControlRequest</b> input parameters as follows:

<ul>
<li>
<i>IoControlCode</i> is set to IOCTL_ACPI_ASYNC_EVAL_METHOD.

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
<i>OutputBuffer</i> supplies a pointer to an <a href="..\acpiioct\ns-acpiioct-_acpi_eval_output_buffer_v1.md">ACPI_EVAL_OUTPUT_BUFFER</a> structure that contains the output arguments from the control method.

</li>
<li>
<i>IoStatusBlock</i> is set to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure.

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



A driver for a device can use IOCTL_ACPI_ASYNC_EVAL_METHOD to asynchronously evaluate a control method that the device supports. For example, if the device is named 'ABCD' in an ACPI namespace and the 'ABCD' device supports a method named '_FOO,' this IOCTL can be used to evaluate control method '_FOO' by sending the request to the 'ABCD' device and supplying the control method name '_FOO.' 

IOCTL_ACPI_ASYNC_EVAL_METHOD supports the following types of input buffer structures:


<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_v1.md">ACPI_EVAL_INPUT_BUFFER</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v1.md">ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_simple_string_v1.md">ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_complex_v1.md">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>


The output arguments from the control method are returned in the variable-length <a href="..\acpiioct\ns-acpiioct-_acpi_eval_output_buffer_v1.md">ACPI_EVAL_OUTPUT_BUFFER</a> structure that is supplied by the <i>OutBuffer</i> pointer. The ACPI_EVAL_OUTPUT_BUFFER includes an array of variable-length <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structures, each of which returns an output argument.

For information about how to evaluate ACPI control methods synchronously, see <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>, <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method_ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a>, and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods-synchronously">Evaluating ACPI Control Methods Synchronously</a>.

IOCTL_ACPI_ASYNC_EVAL_METHOD can be used only at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v1.md">ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method_ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_complex_v1.md">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_v1.md">ACPI_EVAL_INPUT_BUFFER</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_output_buffer_v1.md">ACPI_EVAL_OUTPUT_BUFFER</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_eval_input_buffer_simple_string_v1.md">ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20IOCTL_ACPI_ASYNC_EVAL_METHOD control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

