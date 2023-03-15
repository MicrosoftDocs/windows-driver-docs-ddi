---
UID: NS:ntddk._WHEA_ERROR_RECORD
title: _WHEA_ERROR_RECORD (ntddk.h)
description: The WHEA_ERROR_RECORD structure describes an error record that contains error information about a hardware error condition that occurred.
tech.root: whea
ms.date: 03/13/2023
keywords: ["WHEA_ERROR_RECORD structure"]
ms.keywords: "*PWHEA_ERROR_RECORD, PWHEA_ERROR_RECORD, PWHEA_ERROR_RECORD structure pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD, WHEA_ERROR_RECORD structure [WHEA Drivers and Applications], _WHEA_ERROR_RECORD, ntddk/PWHEA_ERROR_RECORD, ntddk/WHEA_ERROR_RECORD, whea.whea_error_record, whearef_dc309156-feee-4cc2-ba75-d39f3f05fa5f.xml"
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
req.typenames: "*PWHEA_ERROR_RECORD, WHEA_ERROR_RECORD, PWHEA_ERROR_RECORD"
f1_keywords:
 - _WHEA_ERROR_RECORD
 - ntddk/_WHEA_ERROR_RECORD
 - PWHEA_ERROR_RECORD
 - ntddk/PWHEA_ERROR_RECORD
 - WHEA_ERROR_RECORD
 - ntddk/WHEA_ERROR_RECORD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_RECORD
 - PWHEA_ERROR_RECORD
 - WHEA_ERROR_RECORD
---

## -description

The **WHEA_ERROR_RECORD** structure describes an [error record](/windows-hardware/drivers/whea/error-records) that contains error information about a hardware error condition that occurred.

## -struct-fields

### -field Header

A [**WHEA_ERROR_RECORD_HEADER**](./ns-ntddk-_whea_error_record_header.md) structure that describes general information about the hardware error condition.

### -field SectionDescriptor

A variable sized array of [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structures that describe each of the sections of error information that are contained in the error record. The number of structures in the array is specified by the **Header.SectionCount** member of the WHEA_ERROR_RECORD structure.

## -remarks

When a hardware error occurs, WHEA creates an [error record](/windows-hardware/drivers/whea/error-records) to store the error information associated with the hardware error condition. Each error record is described by a WHEA_ERROR_RECORD structure. The Windows kernel includes the error record with the Event Tracing for Windows (ETW) hardware error event that it raises in response to the error so that the error record is saved in the system event log.

The format of the error records that are used by WHEA are based on the *Common Platform Error Record* as described in Appendix N of version 2.2 of the [Unified Extensible Firmware Interface (UEFI) Specification](https://uefi.org/specifications).

A user-mode application can retrieve the error record from the hardware error event for analysis. For more information about how to develop an application to retrieve error records from hardware error events, see [WHEA Hardware Error Event Processing Applications](/windows-hardware/drivers/whea/whea-hardware-error-event-processing-applications).

## -see-also

[**WHEA_ERROR_RECORD_HEADER**](./ns-ntddk-_whea_error_record_header.md)

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)