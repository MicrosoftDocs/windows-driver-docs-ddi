---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1
title: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1 (acpiioct.h)
description: The ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input argument of type ULONG.
old-location: acpi\acpi_eval_input_buffer_simple_integer.htm
tech.root: acpi
ms.assetid: 524e3533-e43c-44eb-b677-dbd023ab5abc
ms.date: 02/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1 structure [ACPI Devices], P_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, P_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1 structure [ACPI Devices], acpi-meth-eval-ref_d9366d11-027b-42e3-bb47-c3b14da27ba4.xml, acpi.acpi_eval_input_buffer_simple_integer, acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, acpiioct/P_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Acpiioct.h
api_name:
-	_ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1
product:
- Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1, ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_V1 structure


## -description


The ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER structure is used as input to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536148">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536145">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method and an input argument of type ULONG.


## -struct-fields




### -field Signature

The signature of an integer input buffer, which must be set to ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_SIGNATURE.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.MethodName

A four-element ASCII character array that contains the name of a control method, for example, 'ABCD.'


### -field DUMMYUNIONNAME.MethodNameAsUlong

A value of type ULONG that contains the name of the method in the format (ULONG) ('DCBA'), where the method name is the four-element ASCII character array 'ABCD.'


### -field IntegerArgument

An argument value of type ULONG that is passed as input to the control method.


## -remarks



If a device supports a control method named ABCD that takes one integer argument of type ULONG, a driver for the device can evaluate the method by sending an IOCTL_EVAL_METHOD request or an IOCTL_ACPI_ASYNC_EVAL_METHOD request to the device and setting the members of the input ACPI_EVAL_INPUT_BUFFER structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_SIMPLE_INTEGER_SIGNATURE.

</li>
<li>
Set <b>MethodName</b> to 'ABCD' or <b>MethodNameAsUlong</b> to (ULONG)('DCBA').

</li>
<li>
Set <b>IntegerArgument</b> to the input integer value.

</li>
</ul>
For more information about how to use this structure, see <a href="https://msdn.microsoft.com/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536145">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536148">IOCTL_ACPI_EVAL_METHOD</a>
 

 

