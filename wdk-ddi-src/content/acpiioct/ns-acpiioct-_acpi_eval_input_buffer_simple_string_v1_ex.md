---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX
title: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX (acpiioct.h)
description: The ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request.
old-location: acpi\acpi_eval_input_buffer_simple_string_ex.htm
tech.root: acpi
ms.assetid: 47991f08-b67d-45f9-ad39-567b6c23c545
ms.date: 02/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, acpi-meth-eval-ref_f58bbb60-e173-408c-a95f-a486eec6d32a.xml, acpi.acpi_eval_input_buffer_simple_string_ex, acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX"
ms.topic: struct
f1_keywords:
 - "acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX"
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
- ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX
product:
- Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V1_EX structure


## -description


The ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_EX structure is used as input to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a> request and to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method_ex">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a> request. The structure supplies the path and name of a control method in an ACPI namespace and an input argument that is an ASCII string. 


## -struct-fields




### -field Signature

The signature of an extended string input buffer that must be set to ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_SIGNATURE_EX. 


### -field MethodName

A NULL-terminated ASCII string that contains the path and name of a control method in an ACPI namespace. The maximum number of characters that the string can contain, including a NULL terminator, is 256. For more information about how to supply the path and name of a control method, see the Remarks section later in this topic.


### -field StringLength

The number of ASCII characters in the array of characters that is supplied by <b>String</b>.


### -field String

An ASCII character array that contains the number of characters that is specified by <b>StringLength</b>. The character array does not include a NULL terminator. 


## -remarks



A driver for a device can use an IOCTL_ACPI_EVAL_METHOD_EX request or an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request to evaluate a control method that is a descendant child object of the device. If the method takes a single string input argument, these requests take an input ACPI_EVAL_INPUT_BUFFER_STRING_EX structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_SIGNATURE_EX.

</li>
<li>
Set <b>MethodName</b> to a NULL-terminated string that supplies either the full path and name to a control method in the ACPI namespace or the path and name of the method that is relative to the device to which the evaluation request is sent. 

For example, assume that a request is sent to a device named 'ABCD,' which is an immediate child of the root of an ACPI namespace, that 'ABCD' device supports a child device named 'CHLD,' and that the 'CHLD' device supports a method named '_FOO.' In this case, the evaluation request can supply either '\ABCD.CHLD._FOO,' which is the fully qualified path and name of the control method in the ACPI namespace, or 'CHLD._FOO,' which is the path and name of the control method that is relative to the 'ABCD' device in the ACPI namespace. 

For more information about how to obtain the fully qualified path and name of a control method in an ACPI namespace, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.

</li>
<li>
Set <b>StringLength</b> to the number of characters in <b>String</b>.

</li>
<li>
Set <b>String</b> to the input string.

</li>
</ul>
For more information about how to use this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method_ex">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a>
 

 

