---
UID: NS:acpiioct._ACPI_EVAL_OUTPUT_BUFFER_V1
title: _ACPI_EVAL_OUTPUT_BUFFER_V1 (acpiioct.h)
description: The ACPI_EVAL_OUTPUT_BUFFER structure contains output arguments from an ACPI control method.
old-location: acpi\acpi_eval_output_buffer.htm
tech.root: acpi
ms.assetid: 3bfb43dd-b4e1-49ee-9be6-c9861341daa1
ms.date: 02/15/2018
keywords: ["_ACPI_EVAL_OUTPUT_BUFFER_V1 structure"]
ms.keywords: "*PACPI_EVAL_OUTPUT_BUFFER, *PACPI_EVAL_OUTPUT_BUFFER_V1, ACPI_EVAL_OUTPUT_BUFFER, ACPI_EVAL_OUTPUT_BUFFER_V1, ACPI_EVAL_OUTPUT_BUFFER_V1 structure [ACPI Devices], _ACPI_EVAL_OUTPUT_BUFFER_V1, acpi-meth-eval-ref_438f3766-37fd-449b-8084-26f08c2f82a0.xml, acpi.acpi_eval_output_buffer, acpiioct/ACPI_EVAL_OUTPUT_BUFFER_V1"
f1_keywords:
 - "acpiioct/ACPI_EVAL_OUTPUT_BUFFER_V1"
 - "ACPI_EVAL_OUTPUT_BUFFER_V1"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 2000.
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
- ACPI_EVAL_OUTPUT_BUFFER_V1
product:
- Windows
targetos: Windows
req.typenames: ACPI_EVAL_OUTPUT_BUFFER_V1, ACPI_EVAL_OUTPUT_BUFFER, *PACPI_EVAL_OUTPUT_BUFFER
---

# _ACPI_EVAL_OUTPUT_BUFFER_V1 structure


## -description


The <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure contains output arguments from an ACPI control method.


## -struct-fields




### -field Signature

The signature of the output buffer, which must be set to ACPI_EVAL_OUTPUT_BUFFER_SIGNATURE.


### -field Length

The size, in bytes, of the output buffer. This size includes the storage for the <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure at the start of the output buffer, plus any additional storage that might be required for data in the <b>Argument</b> array that extends past the end of the <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure.


### -field Count

The number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a> structures that the <b>Argument</b> array contains.


### -field Argument

An array of <b>ACPI_METHOD_ARGUMENT</b> structures. For more information, see Remarks.


## -remarks



The following ACPI IOCTLs return output arguments from ACPI control methods in an <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method_ex">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method">IOCTL_ACPI_EVAL_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a>


Typically, the <b>Argument</b> member is the start of an array of  one or more <b>ACPI_METHOD_ARGUMENT</b> structures. If the array contains more than one <b>ACPI_METHOD_ARGUMENT</b> structure, the additional structures follow the end of the <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure. However, these <b>ACPI_METHOD_ARGUMENT</b> structures form a true array only if none of the <b>DataLength</b> members of these structures has a value greater than <b>sizeof</b>(ULONG). For some types of data, the <b>DataLength</b> value in one or more of these structures can be greater than <b>sizeof</b>(ULONG), in which case the offsets between adjacent <b>ACPI_METHOD_ARGUMENT</b> structures can vary.

For more information about how to use <b>ACPI_EVAL_OUTPUT_BUFFER</b> structures to retrieve output arguments from an ACPI control method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a>
 

 

