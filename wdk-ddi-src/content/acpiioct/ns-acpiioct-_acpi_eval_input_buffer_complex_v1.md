---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
title: _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 (acpiioct.h)
description: The ACPI_EVAL_INPUT_BUFFER_COMPLEX structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input array of ACPI_METHOD_ARGUMENT structures.
old-location: acpi\acpi_eval_input_buffer_complex.htm
tech.root: acpi
ms.date: 02/15/2018
keywords: ["ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure"]
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_COMPLEX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, acpi-meth-eval-ref_e853be71-ec5f-41d6-82fc-6351a0847be8.xml, acpi.acpi_eval_input_buffer_complex, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 and later versions of Windows.
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
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX
f1_keywords:
 - _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
 - acpiioct/_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
 - PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
 - acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
 - ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
 - acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Acpiioct.h
api_name:
 - ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure


## -description

The ACPI_EVAL_INPUT_BUFFER_COMPLEX structure is used as input to an <a href="/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method and an input array of <a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a> structures.

## -struct-fields

### -field Signature

The signature of a complex input buffer, which must be set to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.MethodName

A four-element ASCII character array that contains the name of the method. For example, 'ABCD.'

### -field DUMMYUNIONNAME.MethodNameAsUlong

A value of type ULONG that contains the name of the method in the format (ULONG) ('DCBA'), where the method name is the four-element ASCII character array 'ABCD.'

### -field Size

The number of bytes that the <b>Argument</b> array contains.

### -field ArgumentCount

The number of variable-length ACPI_METHOD_ARGUMENT structures that the <b>Argument</b> array contains. The <b>Argument</b> array can hold a maximum of seven argument structures.

### -field Argument

An array of ACPI_METHOD_ARGUMENT structures.

## -remarks

If a device supports a control method named 'ABCD' that takes an array of arguments as input, a driver for the device can evaluate the method by sending an IOCTL_ACPI_EVAL_METHOD request or an IOCTL_ACPI_ASYNC_EVAL_METHOD request to the device and setting the members of the input ACPI_EVAL_INPUT_BUFFER_COMPLEX structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE.

</li>
<li>
Set <b>MethodName</b> to 'ABCD' or <b>MethodNameAsUlong</b> to (ULONG)('DCBA').

</li>
<li>
Set <b>Size</b> to the number of bytes in the <b>Argument</b> array.

</li>
<li>
Set <b>Argument</b> count to the number of arguments in the <b>Argument</b> array.

</li>
<li>
Set <b>Argument</b> to the array of ACPI_METHOD_ARGUMENT structures.

</li>
</ul>
For more information about how to use this structure, see <a href="/windows-hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a>



<a href="/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a>
