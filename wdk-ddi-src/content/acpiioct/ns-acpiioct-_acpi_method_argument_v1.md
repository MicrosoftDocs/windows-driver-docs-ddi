---
UID: NS:acpiioct._ACPI_METHOD_ARGUMENT_V1
title: _ACPI_METHOD_ARGUMENT_V1 (acpiioct.h)
description: The ACPI_METHOD_ARGUMENT structure contains the value of an input or output argument of an ACPI control method.
old-location: acpi\acpi_method_argument.htm
tech.root: acpi
ms.assetid: 4038d5a5-9ce7-44cb-a6f0-3033617cfe6a
ms.date: 02/15/2018
ms.keywords: "*PACPI_METHOD_ARGUMENT, *PACPI_METHOD_ARGUMENT_V1, ACPI_METHOD_ARGUMENT, ACPI_METHOD_ARGUMENT_V1, ACPI_METHOD_ARGUMENT_V1 structure [ACPI Devices], _ACPI_METHOD_ARGUMENT_V1, acpi-meth-eval-ref_a8988425-e05b-4e85-a345-31a367dec427.xml, acpi.acpi_method_argument, acpiioct/ACPI_METHOD_ARGUMENT_V1"
ms.topic: struct
f1_keywords:
 - "acpiioct/ACPI_METHOD_ARGUMENT_V1"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Acpiioct.h
api_name:
- ACPI_METHOD_ARGUMENT_V1
product:
- Windows
targetos: Windows
req.typenames: ACPI_METHOD_ARGUMENT_V1, ACPI_METHOD_ARGUMENT
---

# _ACPI_METHOD_ARGUMENT_V1 structure


## -description


The ACPI_METHOD_ARGUMENT structure contains the value of an input or output argument of an ACPI control method.


## -struct-fields




### -field Type

The type of the method argument, as specified by one of the following:





#### ACPI_METHOD_ARGUMENT_INTEGER

<b>Argument</b> contains an integer value of type ULONG.



#### ACPI_METHOD_ARGUMENT_STRING

The <b>Data</b> array contains a NULL-terminated ASCII string, and <b>DataLength</b> supplies the number of characters in the string, including the NULL terminator.



#### ACPI_METHOD_ARGUMENT_BUFFER

The <b>Data</b> array contains custom data, and <b>DataLength</b> supplies the number of consecutive array elements that contain the custom data, beginning with the <b>Data</b>[0] element.



#### ACPI_METHOD_ARGUMENT_PACKAGE

The <b>Data</b> array contains an ACPI package descriptor and <b>DataLength</b> supplies the number of consecutive array elements that contain the package descriptor, beginning with the <b>Data</b>[0] element. 


### -field DataLength

The number of UCHAR elements in the <b>Data</b> array that contains the argument data.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.Argument

An argument value of type ULONG.


### -field DUMMYUNIONNAME.Data

An array of values of type UCHAR that contains argument data.


## -remarks



An ACPI_EVAL_OUTPUT_BUFFER structure includes an <b>Argument</b> array of ACPI_METHOD_ARGUMENT structures. The following IOCTLs evaluate control methods and return output arguments in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_output_buffer_v1">ACPI_EVAL_OUTPUT_BUFFER</a> structure:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method_ex">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a>


The ACPI_METHOD_ARGUMENT structure is also used to supply an array of complex input arguments to a control method. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1_ex">ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX</a> structures includes an <b>Argument</b> array of type ACPI_METHOD_ARGUMENT.

For more information about how to use ACPI_METHOD_ARGUMENT structures to supply and retrieve argument data to an ACPI control method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1_ex">ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_output_buffer_v1">ACPI_EVAL_OUTPUT_BUFFER</a>
 

 

