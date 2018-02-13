---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_V2
title: "_ACPI_EVAL_INPUT_BUFFER_V2"
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_V2 structure.
old-location: acpi\acpi_eval_input_buffer_v2.htm
old-project: acpi
ms.assetid: EDB4862E-FAD4-4AB2-BF0C-CF4C6342F0E4
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: PACPI_EVAL_INPUT_BUFFER_V2, acpi.acpi_eval_input_buffer_v2, _ACPI_EVAL_INPUT_BUFFER_V2, acpiioct/ACPI_EVAL_INPUT_BUFFER_V2, *PACPI_EVAL_INPUT_BUFFER_V2, ACPI_EVAL_INPUT_BUFFER_V2, PACPI_EVAL_INPUT_BUFFER_V2 structure pointer [ACPI Devices], ACPI_EVAL_INPUT_BUFFER_V2 structure [ACPI Devices], acpiioct/PACPI_EVAL_INPUT_BUFFER_V2
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
-	ACPI_EVAL_INPUT_BUFFER_V2
product: Windows
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_V2, *PACPI_EVAL_INPUT_BUFFER_V2
---

# _ACPI_EVAL_INPUT_BUFFER_V2 structure


## -description


This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_V2</b> structure.


## -syntax


````
typedef struct _ACPI_EVAL_INPUT_BUFFER_V2 {
  ULONG Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
} ACPI_EVAL_INPUT_BUFFER_V2, *PACPI_EVAL_INPUT_BUFFER_V2;
````


## -struct-fields




### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.


### -field DUMMYUNIONNAME

Defines the method name member of <b>DUMMYUNIONNAME</b>.


### -field DUMMYUNIONNAME.MethodName

 


### -field DUMMYUNIONNAME.MethodNameAsUlong

 



