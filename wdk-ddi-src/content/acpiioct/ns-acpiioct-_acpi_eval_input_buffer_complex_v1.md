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
ms.keywords: acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure pointer [ACPI Devices], *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, acpi-meth-eval-ref_e853be71-ec5f-41d6-82fc-6351a0847be8.xml, *PACPI_EVAL_INPUT_BUFFER_COMPLEX, ACPI_EVAL_INPUT_BUFFER_COMPLEX, acpi.acpi_eval_input_buffer_complex, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, *PACPI_EVAL_INPUT_BUFFER_COMPLEX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, ACPI_EVAL_INPUT_BUFFER_COMPLEX
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure


## -description


The ACPI_EVAL_INPUT_BUFFER_COMPLEX structure is used as input to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a> request and to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a> request. The structure supplies the name of a control method and an input array of <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structures.


## -syntax


````
typedef struct _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 {
  ULONG                Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
  ULONG                Size;
  ULONG                ArgumentCount;
  ACPI_METHOD_ARGUMENT Argument[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1;
````


## -struct-fields




### -field Signature

The signature of a complex input buffer, which must be set to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE. 


### -field DUMMYUNIONNAME



#### MethodName

A four-element ASCII character array that contains the name of the method. For example, 'ABCD.'



#### MethodNameAsUlong

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

<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>



<a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1 structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

