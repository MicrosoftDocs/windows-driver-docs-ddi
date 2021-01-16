---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
title: _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX (acpiioct.h)
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure.
old-location: acpi\acpi_eval_input_buffer_complex_v2_ex.htm
tech.root: acpi
ms.date: 02/15/2018
keywords: ["ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure"]
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, acpi.acpi_eval_input_buffer_complex_v2_ex, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
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
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
f1_keywords:
 - _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - acpiioct/_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Acpiioct.h
api_name:
 - _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
 - ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure


## -description

This topic describes the <b>ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX</b> structure.

## -struct-fields

### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.

### -field MethodName

### -field Size

Defines the <b>ULONG</b> member <b>Size</b>.

### -field ArgumentCount

Defines the <b>ULONG</b> member <b>ArgumentCount</b>.

### -field Argument

 




#### - Argument[ANYSIZE_ARRAY]

Defines the <b>ACPI_METHOD_ARGUMENT_V2</b> member <b>Argument[ANYSIZE_ARRAY]</b>.


#### - MethodName[256]

NULL terminated name string.

