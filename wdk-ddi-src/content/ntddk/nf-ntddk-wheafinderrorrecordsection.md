---
UID: NF:ntddk.WheaFindErrorRecordSection
title: WheaFindErrorRecordSection function (ntddk.h)
description: The WheaFindErrorRecordSection function searches for a specified Windows Hardware Error Architecture (WHEA) error record section within a WHEA error record. The error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.
tech.root: whea
ms.date: 12/07/2022
keywords: ["WheaFindErrorRecordSection function"]
ms.keywords: WheaFindErrorRecordSection, WheaFindErrorRecordSection function [WHEA Drivers and Applications], ntddk/WheaFindErrorRecordSection, whea.wheafinderrorrecordsection, whearef2_fe7f8220-081d-475c-9230-d59cff81164d.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.irql: IRQL <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WheaFindErrorRecordSection
 - ntddk/WheaFindErrorRecordSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaFindErrorRecordSection
---

## -description

The **WheaFindErrorRecordSection** function searches for a specified Windows Hardware Error Architecture (WHEA) error record section within a WHEA [error record](/windows-hardware/drivers/whea/error-records). The error record section is formatted as a [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure.

## -parameters

### -param Record [in]

A pointer to a WHEA [error record](/windows-hardware/drivers/whea/error-records) that is formatted as a [**WHEA_ERROR_RECORD**](./ns-ntddk-_whea_error_record.md) structure.

### -param SectionType [in]

A GUID that specifies the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure to be located within the specified WHEA [error record](/windows-hardware/drivers/whea/error-records).

### -param SectionDescriptor [out]

The address of a [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) pointer.

If the **WheaFindErrorRecordSection** function locates the specified WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure, the function sets the *SectionDescriptor* parameter to the address of that structure within the specified WHEA [error record](/windows-hardware/drivers/whea/error-records).

### -param SectionData [out, optional]

The address of a PVOID pointer.

If the **WheaFindErrorRecordSection** function locates the specified [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure, the function sets the *SectionData* parameter to the address of the hardware error data associated with that descriptor within the specified WHEA [error record](/windows-hardware/drivers/whea/error-records).

This parameter is optional and must be set to **NULL** if a pointer to the hardware error data is not required.

## -returns

**WheaFindErrorRecordSection** returns one of the following NTSTATUS codes:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The specified [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure was found. |
| **STATUS_NOT_FOUND** | The specified [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure was not found. |
| **STATUS_INVALID_PARAMETER** | Either the *Record*, *SectionType,* or *SectionDescriptor* parameters were set to **NULL**, or the WHEA [error record](/windows-hardware/drivers/whea/error-records) referenced through the *Record* parameter is invalid. |

## -remarks

If **WheaFindErrorRecordSection** returns STATUS_SUCCESS, it has located the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure that was specified through the *Guid* parameter. **WheaFindErrorRecordSection** sets the *SectionDescriptor* parameter to the address of the located **WHEA_ERROR_RECORD_SECTION_DESCRIPTOR** structure.

Additionally, if **WheaFindErrorRecordSection** returns STATUS_SUCCESS and the caller set the *SectionData* parameter to the address of a PVOID pointer variable, the function updates the parameter with the address of the hardware error data associated with the specified [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure.

The format of the hardware error data is dependent upon the **SectionType** member of the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure referenced through the *SectionDescriptor* parameter. For example, if the **SectionType** member has the value PROCESSOR_GENERIC_ERROR_SECTION_GUID, the hardware error data is formatted as a [**WHEA_PROCESSOR_GENERIC_ERROR_SECTION**](./ns-ntddk-_whea_processor_generic_error_section.md) structure.

## -see-also

[Error record](/windows-hardware/drivers/whea/error-records)

[**WHEA_ERROR_RECORD**](./ns-ntddk-_whea_error_record.md)

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)