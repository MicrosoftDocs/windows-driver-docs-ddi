---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
title: "_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1"
author: windows-driver-content
description: The ACPI_EVAL_INPUT_BUFFER_COMPLEX structure is used as input to an IOCTL_ACPI_EVAL_METHOD request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD request. The structure supplies the name of a control method and an input array of ACPI_METHOD_ARGUMENT structures.
old-location: acpi\acpi_eval_input_buffer_complex.htm
old-project: acpi
ms.assetid: 6b59fa86-3c3b-4ab9-98e2-f62f028d53df
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_COMPLEX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, acpi-meth-eval-ref_e853be71-ec5f-41d6-82fc-6351a0847be8.xml, acpi.acpi_eval_input_buffer_complex, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
product:
- Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure


## -description


The ACPI_EVAL_INPUT_BUFFER_COMPLEX structure is used as input to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536148">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536145">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method and an input array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff536125">ACPI_METHOD_ARGUMENT</a> structures.


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
For more information about how to use this structure, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536125">ACPI_METHOD_ARGUMENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536145">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536148">IOCTL_ACPI_EVAL_METHOD</a>
 

 

