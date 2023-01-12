---
UID: NE:ntddk._WHEA_ERROR_SEVERITY
title: WHEA_ERROR_SEVERITY (ntddk.h)
description: The WHEA_ERROR_SEVERITY enumeration defines the possible severity levels of a hardware error condition.
tech.root: whea
ms.date: 12/06/2022
keywords: ["WHEA_ERROR_SEVERITY enumeration"]
ms.keywords: "*PWHEA_ERROR_SEVERITY, PWHEA_ERROR_SEVERITY, PWHEA_ERROR_SEVERITY enumeration pointer [WHEA Drivers and Applications], WHEA_ERROR_SEVERITY, WHEA_ERROR_SEVERITY enumeration [WHEA Drivers and Applications], WheaErrSevCorrected, WheaErrSevFatal, WheaErrSevInformational, WheaErrSevRecoverable, _WHEA_ERROR_SEVERITY, ntddk/PWHEA_ERROR_SEVERITY, ntddk/WHEA_ERROR_SEVERITY, ntddk/WheaErrSevCorrected, ntddk/WheaErrSevFatal, ntddk/WheaErrSevInformational, ntddk/WheaErrSevRecoverable, whea.whea_error_severity, whearef_e9b0fee6-a6cf-4f61-a3b6-ef53553aa3ff.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
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
targetos: Windows
req.typenames: WHEA_ERROR_SEVERITY, *PWHEA_ERROR_SEVERITY
f1_keywords:
 - _WHEA_ERROR_SEVERITY
 - ntddk/_WHEA_ERROR_SEVERITY
 - PWHEA_ERROR_SEVERITY
 - ntddk/PWHEA_ERROR_SEVERITY
 - WHEA_ERROR_SEVERITY
 - ntddk/WHEA_ERROR_SEVERITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_SEVERITY
 - PWHEA_ERROR_SEVERITY
 - WHEA_ERROR_SEVERITY
---

## -description

The **WHEA_ERROR_SEVERITY** enumeration defines the possible severity levels of a hardware error condition.

## -enum-fields

### -field WheaErrSevRecoverable

The error has not been corrected but might be recoverable.

### -field WheaErrSevFatal

The error has not been corrected and is fatal.

### -field WheaErrSevCorrected

The error has been corrected by the hardware or firmware.

### -field WheaErrSevInformational

An error has not occurred.

## -remarks

The [**WHEA_ERROR_PACKET**](./ns-ntddk-_whea_error_packet_v2.md), [**WHEA_ERROR_RECORD_HEADER**](./ns-ntddk-_whea_error_record_header.md), [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md), and [**WHEA_GENERIC_ERROR**](./ns-ntddk-_whea_generic_error.md) structures each contain a member of type WHEA_ERROR_SEVERITY that specifies the severity of the error that is described by the structure.

## -see-also

[**WHEA_ERROR_PACKET**](./ns-ntddk-_whea_error_packet_v2.md)

[**WHEA_ERROR_RECORD_HEADER**](./ns-ntddk-_whea_error_record_header.md)

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)

[**WHEA_GENERIC_ERROR**](./ns-ntddk-_whea_generic_error.md)