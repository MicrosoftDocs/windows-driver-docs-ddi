---
UID: NS:acpiioct._ACPI_GET_DEVICE_SPECIFIC_DATA
title: "_ACPI_GET_DEVICE_SPECIFIC_DATA"
author: windows-driver-content
description: The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method.
old-location: acpi\acpi_get_device_specific_data.htm
old-project: acpi
ms.assetid: F7B4E80F-AB83-4E0F-9933-D953744A1970
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: PACPI_GET_DEVICE_SPECIFIC_DATA structure pointer [ACPI Devices], PACPI_GET_DEVICE_SPECIFIC_DATA, ACPI_GET_DEVICE_SPECIFIC_DATA structure [ACPI Devices], *PACPI_GET_DEVICE_SPECIFIC_DATA, _ACPI_GET_DEVICE_SPECIFIC_DATA, acpiioct/ACPI_GET_DEVICE_SPECIFIC_DATA, acpiioct/PACPI_GET_DEVICE_SPECIFIC_DATA, ACPI_GET_DEVICE_SPECIFIC_DATA, acpi.acpi_get_device_specific_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ACPI_GET_DEVICE_SPECIFIC_DATA
product: Windows
targetos: Windows
req.typenames: ACPI_GET_DEVICE_SPECIFIC_DATA, *PACPI_GET_DEVICE_SPECIFIC_DATA
---

# _ACPI_GET_DEVICE_SPECIFIC_DATA structure


## -description


The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method.


## -syntax


````
typedef struct _ACPI_GET_DEVICE_SPECIFIC_DATA {
  ULONG Signature;
  GUID  Section;
  ULONG PropertyNameLength;
  UCHAR PropertyName[ANYSIZE_ARRAY];
} ACPI_GET_DEVICE_SPECIFIC_DATA, *PACPI_GET_DEVICE_SPECIFIC_DATA;
````


## -struct-fields




### -field Signature

A unique identifier for the IOCTL.


### -field Section

A GUID specified by the caller.


### -field PropertyNameLength

The length of the property name.


### -field PropertyName

Specifies the property name. If not specified, the <b>PropertyNameLength</b> and the <b>PropertyName</b> are returned. If a <b>PropertyName</b> is specified, only the value of that <b>PropertyName</b> is returned.

