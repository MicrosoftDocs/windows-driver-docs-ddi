---
UID: NF:ntddk.WheaFindNextErrorRecordSection
title: WheaFindNextErrorRecordSection function (ntddk.h)
description: The WheaFindNextErrorRecordSection function allows a caller to iteratively examine the WHEA error record sections within a WHEA error record. Each error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.
tech.root: whea
ms.date: 12/07/2022
keywords: ["WheaFindNextErrorRecordSection function"]
ms.keywords: WheaFindNextErrorRecordSection, WheaFindNextErrorRecordSection function [WHEA Drivers and Applications], ntddk/WheaFindNextErrorRecordSection, whea.wheafindnexterrorrecordsection, whearef2_9beb5b85-6c25-49e5-9abc-bcb8e343c8c9.xml
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
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WheaFindNextErrorRecordSection
 - ntddk/WheaFindNextErrorRecordSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaFindNextErrorRecordSection
---

## -description

The **WheaFindNextErrorRecordSection** function allows a caller to iteratively examine the WHEA error record sections within a WHEA [error record](/windows-hardware/drivers/whea/error-records). Each error record section is formatted as a [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure.

## -parameters

### -param Record [in]

A pointer to a WHEA [error record](/windows-hardware/drivers/whea/error-records) that is formatted as a [**WHEA_ERROR_RECORD**](./ns-ntddk-_whea_error_record.md) structure.

### -param Context [in, out]

A pointer to a ULONG variable that maintains the current state of the search.

This variable must be initialized to zero before the first call to the **WheaFindNextErrorRecordSection** function.

### -param SectionDescriptor [out]

The address of a [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) pointer.

If the **WheaFindNextErrorRecordSection** function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure within the specified WHEA [error record](/windows-hardware/drivers/whea/error-records), the function sets the *SectionDescriptor* parameter to the address of that structure within the specified WHEA error record.

### -param SectionData [out, optional]

The address of a PVOID pointer.

If the **WheaFindNextErrorRecordSection** function locates the next [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure within the specified WHEA [error record](/windows-hardware/drivers/whea/error-records), the function sets the *SectionData* parameter to the address of the hardware error data associated with that descriptor.

This parameter is optional and must be set to **NULL** if a pointer to the error record section data is not required.

## -returns

**WheaFindNextErrorRecordSection** returns one of the following NTSTATUS codes:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The next [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure was found. |
| **STATUS_NOT_FOUND** | The next [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure was not found. |
| **STATUS_INVALID_PARAMETER** | Either the *Record*, *SectionType,* or *SectionDescriptor* parameters were set to **NULL**, or the [**WHEA_ERROR_RECORD**](./ns-ntddk-_whea_error_record.md) data referenced through the *Record* parameter is invalid. |

## -remarks

If the *Context* parameter is set to 0, **WheaFindNextErrorRecordSection** returns a pointer to the first [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure within a WHEA [error record](/windows-hardware/drivers/whea/error-records). **WheaFindNextErrorRecordSection** will also update the *Context* parameter with state information related to the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR returned through the *SectionDescriptor* parameter.

On subsequent calls to **WheaFindNextErrorRecordSection**, the function returns the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure (if available) within the WHEA error record. If the function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure, it will update the *Context* parameter. Otherwise, the function will return STATUS_NOT_FOUND.

In order to locate the first [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) within the specified WHEA [error record](/windows-hardware/drivers/whea/error-records), the caller must set the variable, whose address is passed in the *Context* parameter, to 0 before the calling. After that, the caller must not modify the variable's value when locating the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR through subsequent calls to **WheaFindNextErrorRecordSection**.

Additionally, if **WheaFindNextErrorRecordSection** returns STATUS_SUCCESS and the caller set the *SectionData* parameter to the address of a PVOID pointer variable, the function updates the parameter with the address of the hardware error data associated with the specified [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure.

The format of the hardware error data depends upon the **SectionType** member of the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure that is referenced through the *SectionDescriptor* parameter. For example, if the **SectionType** member has the value PROCESSOR_GENERIC_ERROR_SECTION_GUID, the hardware error data is formatted as a [**WHEA_PROCESSOR_GENERIC_ERROR_SECTION**](./ns-ntddk-_whea_processor_generic_error_section.md) structure.

## -see-also

[Error record](/windows-hardware/drivers/whea/error-records)

[**WHEA_ERROR_PACKET**](/previous-versions/windows/hardware/drivers/ff560465(v=vs.85))

[**WHEA_ERROR_RECORD**](./ns-ntddk-_whea_error_record.md)

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)