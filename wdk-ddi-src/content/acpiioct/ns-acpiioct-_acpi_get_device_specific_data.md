---
UID: NS:acpiioct._ACPI_GET_DEVICE_SPECIFIC_DATA
title: _ACPI_GET_DEVICE_SPECIFIC_DATA (acpiioct.h)
description: The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method.
old-location: acpi\acpi_get_device_specific_data.htm
tech.root: acpi
ms.assetid: F7B4E80F-AB83-4E0F-9933-D953744A1970
ms.date: 02/15/2018
ms.keywords: "*PACPI_GET_DEVICE_SPECIFIC_DATA, ACPI_GET_DEVICE_SPECIFIC_DATA, ACPI_GET_DEVICE_SPECIFIC_DATA structure [ACPI Devices], PACPI_GET_DEVICE_SPECIFIC_DATA, PACPI_GET_DEVICE_SPECIFIC_DATA structure pointer [ACPI Devices], _ACPI_GET_DEVICE_SPECIFIC_DATA, acpi.acpi_get_device_specific_data, acpiioct/ACPI_GET_DEVICE_SPECIFIC_DATA, acpiioct/PACPI_GET_DEVICE_SPECIFIC_DATA"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Acpiioct.h
api_name:
-	ACPI_GET_DEVICE_SPECIFIC_DATA
product:
- Windows
targetos: Windows
req.typenames: ACPI_GET_DEVICE_SPECIFIC_DATA, *PACPI_GET_DEVICE_SPECIFIC_DATA
---

# _ACPI_GET_DEVICE_SPECIFIC_DATA structure


## -description


The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method.


## -struct-fields




### -field Signature

A unique identifier for the IOCTL.


### -field Section

A GUID specified by the caller.


### -field PropertyNameLength

The length of the property name.


### -field PropertyName

Specifies the property name. If not specified, the <b>PropertyNameLength</b> and the <b>PropertyName</b> are returned. If a <b>PropertyName</b> is specified, only the value of that <b>PropertyName</b> is returned.

