---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX
title: _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX (acpiioct.h)
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure.
old-location: acpi\acpi_eval_input_buffer_simple_string_v2_ex.htm
tech.root: acpi
ms.assetid: 627DA82C-CD51-4FA0-80C2-03F7FA26C0CF
ms.date: 02/15/2018
keywords: ["_ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure"]
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, acpi.acpi_eval_input_buffer_simple_string_v2_ex, acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX"
f1_keywords:
 - "acpiioct/ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX"
 - "ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Acpiioct.h
api_name:
- ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX, *PACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX
---

# _ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX structure


## -description


This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_SIMPLE_STRING_V2_EX</b> structure.


## -struct-fields




### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.


### -field MethodName

 


### -field StringLength

Defines the <b>ULONG</b> member <b>StringLength</b>.


### -field String

 




#### - MethodName[256]

NULL terminated name string.


#### - String[ANYSIZE_ARRAY]

Defines the <b>UCHAR</b> member <b>String[ANYSIZE_ARRAY]</b>.

