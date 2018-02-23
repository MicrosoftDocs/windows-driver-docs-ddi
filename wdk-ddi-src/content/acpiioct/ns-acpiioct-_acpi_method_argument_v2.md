---
UID: NS:acpiioct._ACPI_METHOD_ARGUMENT_V2
title: "_ACPI_METHOD_ARGUMENT_V2"
author: windows-driver-content
description: This topic describes the ACPI_METHOD_ARGUMENT_V2 structure.
old-location: acpi\acpi_method_argument_v2.htm
old-project: acpi
ms.assetid: 10DD32ED-96F2-43BF-BBF4-85851BC9A377
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: acpiioct/ACPI_METHOD_ARGUMENT_V2, acpiioct/PACPI_METHOD_ARGUMENT_V2, acpi.acpi_method_argument_v2, *PACPI_METHOD_ARGUMENT_V2, _ACPI_METHOD_ARGUMENT_V2, PACPI_METHOD_ARGUMENT_V2, PACPI_METHOD_ARGUMENT_V2 structure pointer [ACPI Devices], ACPI_METHOD_ARGUMENT_V2 structure [ACPI Devices], ACPI_METHOD_ARGUMENT_V2
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
-	ACPI_METHOD_ARGUMENT_V2
product: Windows
targetos: Windows
req.typenames: ACPI_METHOD_ARGUMENT_V2
---

# _ACPI_METHOD_ARGUMENT_V2 structure


## -description


This topic describes the  <b>ACPI_METHOD_ARGUMENT_V2</b> structure.


## -syntax


````
typedef struct _ACPI_METHOD_ARGUMENT_V2 {
  USHORT Type;
  USHORT DataLength;
  union {
    ULONG                                 Argument;
     _Field_size_bytes_(DataLength) UCHAR Data[ANYSIZE_ARRAY];
  } DUMMYUNIONNAME;
} ACPI_METHOD_ARGUMENT_V2, *PACPI_METHOD_ARGUMENT_V2;
````


## -struct-fields




### -field Type

Defines the <b>USHORT</b> member <b>Type</b>.


### -field DataLength

Defines the <b>USHORT</b> member <b>DataLength</b>.


### -field DUMMYUNIONNAME

Defines the members of <b>DUMMYUNIONNAME</b>.

