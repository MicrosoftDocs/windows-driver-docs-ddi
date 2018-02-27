---
UID: NS:acpiioct._ACPI_EVAL_OUTPUT_BUFFER_V1
title: "_ACPI_EVAL_OUTPUT_BUFFER_V1"
author: windows-driver-content
description: The ACPI_EVAL_OUTPUT_BUFFER structure contains output arguments from an ACPI control method.
old-location: acpi\acpi_eval_output_buffer.htm
old-project: acpi
ms.assetid: 3bfb43dd-b4e1-49ee-9be6-c9861341daa1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_EVAL_OUTPUT_BUFFER, *PACPI_EVAL_OUTPUT_BUFFER_V1, ACPI_EVAL_OUTPUT_BUFFER, ACPI_EVAL_OUTPUT_BUFFER_V1, ACPI_EVAL_OUTPUT_BUFFER_V1 structure [ACPI Devices], _ACPI_EVAL_OUTPUT_BUFFER_V1, acpi-meth-eval-ref_438f3766-37fd-449b-8084-26f08c2f82a0.xml, acpi.acpi_eval_output_buffer, acpiioct/ACPI_EVAL_OUTPUT_BUFFER_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_EVAL_OUTPUT_BUFFER_V1
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_OUTPUT_BUFFER_V1, ACPI_EVAL_OUTPUT_BUFFER, *PACPI_EVAL_OUTPUT_BUFFER
---

# _ACPI_EVAL_OUTPUT_BUFFER_V1 structure


## -description


The <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure contains output arguments from an ACPI control method.


## -syntax


````
typedef struct _ACPI_EVAL_OUTPUT_BUFFER_V1 {
  ULONG                Signature;
  ULONG                Length;
  ULONG                Count;
  ACPI_METHOD_ARGUMENT Argument[ANYSIZE_ARRAY];
} ACPI_EVAL_OUTPUT_BUFFER_V1;
````


## -struct-fields




### -field Signature

The signature of the output buffer, which must be set to ACPI_EVAL_OUTPUT_BUFFER_SIGNATURE.


### -field Length

The size, in bytes, of the output buffer. This size includes the storage for the <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure at the start of the output buffer, plus any additional storage that might be required for data in the <b>Argument</b> array that extends past the end of the <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure.


### -field Count

The number of <a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a> structures that the <b>Argument</b> array contains.


### -field Argument

An array of <b>ACPI_METHOD_ARGUMENT</b> structures. For more information, see Remarks.


## -remarks



The following ACPI IOCTLs return output arguments from ACPI control methods in an <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure:


<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method.md">IOCTL_ACPI_ASYNC_EVAL_METHOD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method_ex.md">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method.md">IOCTL_ACPI_EVAL_METHOD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method_ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a>


Typically, the <b>Argument</b> member is the start of an array of  one or more <b>ACPI_METHOD_ARGUMENT</b> structures. If the array contains more than one <b>ACPI_METHOD_ARGUMENT</b> structure, the additional structures follow the end of the <b>ACPI_EVAL_OUTPUT_BUFFER</b> structure. However, these <b>ACPI_METHOD_ARGUMENT</b> structures form a true array only if none of the <b>DataLength</b> members of these structures has a value greater than <b>sizeof</b>(ULONG). For some types of data, the <b>DataLength</b> value in one or more of these structures can be greater than <b>sizeof</b>(ULONG), in which case the offsets between adjacent <b>ACPI_METHOD_ARGUMENT</b> structures can vary.

For more information about how to use <b>ACPI_EVAL_OUTPUT_BUFFER</b> structures to retrieve output arguments from an ACPI control method, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also

<a href="..\acpiioct\ns-acpiioct-_acpi_method_argument_v1.md">ACPI_METHOD_ARGUMENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_EVAL_OUTPUT_BUFFER_V1 structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

