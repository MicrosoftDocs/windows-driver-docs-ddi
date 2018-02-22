---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_V1_EX
title: "_ACPI_EVAL_INPUT_BUFFER_V1_EX"
author: windows-driver-content
description: The ACPI_EVAL_INPUT_BUFFER_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request.
old-location: acpi\acpi_eval_input_buffer_ex.htm
old-project: acpi
ms.assetid: 3a5d4572-0455-4fd0-aeff-fc99d72433b6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PACPI_EVAL_INPUT_BUFFER_V1_EX, *PACPI_EVAL_INPUT_BUFFER_EX, PACPI_EVAL_INPUT_BUFFER_V1_EX structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_V1_EX, acpiioct/ACPI_EVAL_INPUT_BUFFER_V1_EX, ACPI_EVAL_INPUT_BUFFER_V1_EX, ACPI_EVAL_INPUT_BUFFER_V1_EX structure [ACPI Devices], *PACPI_EVAL_INPUT_BUFFER_V1_EX, ACPI_EVAL_INPUT_BUFFER_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_V1_EX, acpi-meth-eval-ref_13d68b28-6366-40cb-84d0-b6dcb7520c93.xml, acpi.acpi_eval_input_buffer_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_EVAL_INPUT_BUFFER_V1_EX
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_V1_EX, *PACPI_EVAL_INPUT_BUFFER_V1_EX, *PACPI_EVAL_INPUT_BUFFER_EX, ACPI_EVAL_INPUT_BUFFER_EX
---

# _ACPI_EVAL_INPUT_BUFFER_V1_EX structure


## -description


The ACPI_EVAL_INPUT_BUFFER_EX structure is used as input to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method_ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a> request and to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method_ex.md">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a> request. The structure supplies the path and name of a control method in an ACPI namespace that does not take an input argument.  


## -syntax


````
typedef struct _ACPI_EVAL_INPUT_BUFFER_V1_EX {
  ULONG Signature;
  CHAR  MethodName[256];
} ACPI_EVAL_INPUT_BUFFER_V1_EX, *PACPI_EVAL_INPUT_BUFFER_V1_EX;
````


## -struct-fields




### -field Signature

The signature of an input buffer that does not include an argument, which must be set to ACPI_EVAL_INPUT_BUFFER_SIGNATURE_EX.


### -field MethodName

A NULL-terminated ASCII string that contains the path and name of a control method in an ACPI namespace. The maximum number of characters that the string can contain, including a NULL-terminator, is 256. For more information about how to supply the path and name of a control method, see the Remarks section later in this topic.


## -remarks



A driver for a device can use an IOCTL_ACPI_EVAL_METHOD_EX request or an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request to evaluate a control method that is a descendant child object of the device. If the method does not take input arguments, these requests take an input ACPI_EVAL_INPUT_BUFFER_EX structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_SIGNATURE_EX.

</li>
<li>
Set <b>MethodName</b> to a NULL-terminated string that supplies either the full path and name to a control method in the ACPI namespace or the path and name of the method that is relative to the device to which the evaluation request is sent. 

For example, assume that a request is sent to a device named 'ABCD' which is an immediate child of the root of an ACPI namespace, that 'ABCD' device supports a child device named 'CHLD,' and that the 'CHLD' device supports a method named '_FOO.' In this case, the evaluation request can supply either '\ABCD.CHLD._FOO,, which is the fully qualified path and name of the control method in the ACPI namespace, or 'CHLD._FOO,' which is the path and name of the control method that is relative to the 'ABCD' device in the ACPI namespace. 

For more information about how to obtain the fully qualified path and name of a control method in an ACPI namespace, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.

</li>
</ul>
For more information about how to use this structure, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.




## -see-also

<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_async_eval_method_ex.md">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_eval_method_ex.md">IOCTL_ACPI_EVAL_METHOD_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_EVAL_INPUT_BUFFER_V1_EX structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

