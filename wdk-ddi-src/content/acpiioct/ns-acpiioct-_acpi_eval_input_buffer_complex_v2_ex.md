---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
title: "_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure.
old-location: acpi\acpi_eval_input_buffer_complex_v2_ex.htm
old-project: acpi
ms.assetid: 50AEF454-8E36-4348-9340-330094D2FDF8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, acpi.acpi_eval_input_buffer_complex_v2_ex, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure pointer [ACPI Devices], ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX structure


## -description


This topic describes the <b>ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX</b> structure.


## -syntax


````
typedef struct _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX {
  ULONG                                               Signature;
  CHAR                                                MethodName[256];
  ULONG                                               Size;
  ULONG                                               ArgumentCount;
  _Field_size_(ArgumentCount) ACPI_METHOD_ARGUMENT_V2 Argument[ANYSIZE_ARRAY];
} ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2_EX;
````


## -struct-fields




### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.


### -field MethodName

 


### -field Size

Defines the <b>ULONG</b> member <b>Size</b>.


### -field ArgumentCount

Defines the <b>ULONG</b> member <b>ArgumentCount</b>.


### -field Argument

 




#### - MethodName[256]

NULL terminated name string.


#### - Argument[ANYSIZE_ARRAY]

Defines the <b>ACPI_METHOD_ARGUMENT_V2</b> member <b>Argument[ANYSIZE_ARRAY]</b>.

