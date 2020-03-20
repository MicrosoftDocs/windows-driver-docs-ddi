---
UID: NI:acpiioct.IOCTL_ACPI_ASYNC_EVAL_METHOD_EX
title: IOCTL_ACPI_ASYNC_EVAL_METHOD_EX (acpiioct.h)
description: A driver for a device can use the IOCTL_ACPI_ASYNC_EVAL_METHOD_EX device control request to asynchronously evaluate an ACPI control method that is supported by a child device of the device.
old-location: acpi\ioctl_acpi_async_eval_method_ex.htm
tech.root: acpi
ms.assetid: fb5c6cbe-b1f4-4aed-afe3-1a4e8e26416e
ms.date: 02/15/2018
keywords: ["IOCTL_ACPI_ASYNC_EVAL_METHOD_EX IOCTL"]
ms.keywords: IOCTL_ACPI_ASYNC_EVAL_METHOD_EX, IOCTL_ACPI_ASYNC_EVAL_METHOD_EX control, IOCTL_ACPI_ASYNC_EVAL_METHOD_EX control code [ACPI Devices], acpi-meth-eval-ref_d6847663-52f2-4ae0-9ee5-defba8aed0cf.xml, acpi.ioctl_acpi_async_eval_method_ex, acpiioct/IOCTL_ACPI_ASYNC_EVAL_METHOD_EX
f1_keywords:
 - "acpiioct/IOCTL_ACPI_ASYNC_EVAL_METHOD_EX"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Acpiioct.h
api_name:
- IOCTL_ACPI_ASYNC_EVAL_METHOD_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_ACPI_ASYNC_EVAL_METHOD_EX IOCTL


## -description


A driver for a device can use the IOCTL_ACPI_ASYNC_EVAL_METHOD_EX device control request to asynchronously evaluate an ACPI control method that is supported by a child device of the device. The driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a> and pass the following input and output parameters to build this request. 


## -ioctlparameters




### -input-buffer

Set the <b>IoBuildDeviceIoControlRequest</b> input parameters as follows:

<ul>
<li>
<i>IoControlCode</i> is set to IOCTL_ACPI_ASYNC_EVAL_METHOD_EX.

</li>
<li>
<i>DeviceObject</i> is set to a pointer to the physical device object (PDO) of the device.

</li>
<li>
<i>InputBuffer</i> is set to a pointer to an input buffer structure that depends on the type of input arguments to be passed to the control method. For more information about the type input arguments that this IOCTL supports, see the Remarks section later in this topic.

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
<i>OutputBuffer</i> supplies a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_output_buffer_v1">ACPI_EVAL_OUTPUT_BUFFER</a> structure that contains the output arguments from the control method.

</li>
<li>
<i>IoStatusBlock</i> is set to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure.

</li>
</ul>

### -output-buffer-length

<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request succeeds, <i>IoStatusBlock</i>-><b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the output buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain all the output arguments from the control method, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW, and <i>OutputBuffer</i>-><b>Length</b> is set to the required length of the output buffer.

If the request succeeds, the <i>IoStatusBlock</i>-><b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.


## -remarks



A driver for a device can use IOCTL_ACPI_ASYNC_EVAL_METHOD_EX to asynchronously evaluate a control method that is supported by a child object in the namespace of the device. The path and name of the control method that is supplied by this request must be either the fully qualified path and name of the method in the ACPI namespace or the path and name of the method relative to the device to which the request is sent. For example, assume that a device named 'ABCD' is an immediate child of the root of an ACPI namespace, that the 'ABCD' device supports a child device named 'CHLD,' and that the 'CHLD' device supports a method named '_FOO.' In this case, to evaluate the '_FOO' method, a driver sends an evaluation request to the 'ABCD' device and supplies either the path and name '\ABCD.CHLD._FOO,' which is the fully qualified path and name in the ACPI namespace, or the path and name 'CHLD._FOO,' which is the path and name relative to the 'ABCD' device in the ACPI namespace.

IOCTL_ACPI_ASYNC_EVAL_METHOD_EX supports the following types of input buffer structures:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_v1_ex">ACPI_EVAL_INPUT_BUFFER_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v1_ex">ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_simple_string_v1_ex">ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1_ex">ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX</a>


The output arguments from the control method are returned in the variable-length <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_output_buffer_v1">ACPI_EVAL_OUTPUT_BUFFER</a> structure that is supplied by the <i>OutBuffer</i> pointer. The ACPI_EVAL_OUTPUT_BUFFER includes an array of variable-length <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a> structures, each one of which returns an output argument.

For information about how to evaluate an ACPI control method synchronously, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/evaluating-acpi-control-methods-synchronously">Evaluating ACPI Control Methods Synchronously</a>.

IOCTL_ACPI_ASYNC_EVAL_METHOD_EX can be used only at IRQL <= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1_ex">ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_v1_ex">ACPI_EVAL_INPUT_BUFFER_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_simple_integer_v1_ex">ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_simple_string_v1_ex">ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_output_buffer_v1">ACPI_EVAL_OUTPUT_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a>
 

 

