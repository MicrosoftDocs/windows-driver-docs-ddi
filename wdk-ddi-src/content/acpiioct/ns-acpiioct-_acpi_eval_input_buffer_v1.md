---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_V1
title: _ACPI_EVAL_INPUT_BUFFER_V1 (acpiioct.h)
description: The ACPI_EVAL_INPUT_BUFFER structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method that does not take an input argument.
old-location: acpi\acpi_eval_input_buffer.htm
tech.root: acpi
ms.assetid: a911fab9-516f-4ac5-ae33-1b6e218f9349
ms.date: 02/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER, *PACPI_EVAL_INPUT_BUFFER_V1, ACPI_EVAL_INPUT_BUFFER, ACPI_EVAL_INPUT_BUFFER_V1, ACPI_EVAL_INPUT_BUFFER_V1 structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_V1, PACPI_EVAL_INPUT_BUFFER_V1 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_V1, acpi-meth-eval-ref_fda162bd-f908-46bf-a5a9-66daeb6b6aaf.xml, acpi.acpi_eval_input_buffer, acpiioct/ACPI_EVAL_INPUT_BUFFER_V1, acpiioct/PACPI_EVAL_INPUT_BUFFER_V1"
f1_keywords:
 - "acpiioct/ACPI_EVAL_INPUT_BUFFER_V1"
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
- ACPI_EVAL_INPUT_BUFFER_V1
product:
- Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_V1, *PACPI_EVAL_INPUT_BUFFER_V1, ACPI_EVAL_INPUT_BUFFER, *PACPI_EVAL_INPUT_BUFFER
---

# _ACPI_EVAL_INPUT_BUFFER_V1 structure


## -description


The ACPI_EVAL_INPUT_BUFFER structure is used as input to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method that does not take an input argument.


## -struct-fields




### -field Signature

The signature of an input buffer that does not include an argument, which must be set to ACPI_EVAL_INPUT_BUFFER_SIGNATURE.


### -field DUMMYUNIONNAME


### -field DUMMYUNIONNAME.MethodName

A four-element ASCII character array that contains the name of a control method, for example, 'ABCD.' 


### -field DUMMYUNIONNAME.MethodNameAsUlong

A value of type ULONG that contains the name of the method in the format (ULONG) ('DCBA'), where the method name is the four-element ASCII character array 'ABCD.' 


## -remarks



If a device supports a control method named 'ABCD' that does not take an input argument, a driver for the device can evaluate the method by sending an IOCTL_ACPI_EVAL_METHOD request or an IOCTL_ACPI_ASYNC_EVAL_METHOD request to the device and setting the members of the input ACPI_EVAL_INPUT_BUFFER structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_SIGNATURE.

</li>
<li>
Set <b>MethodName</b> to 'ABCD' or <b>MethodNameAsUlong</b> to (ULONG)('DCBA').

</li>
</ul>
For more information about how to use this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a>
 

 

