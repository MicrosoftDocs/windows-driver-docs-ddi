---
UID: NF:ntddk.WheaHwErrorReportSetSectionNameDeviceDriver
title: WheaHwErrorReportSetSectionNameDeviceDriver
tech.root: whea
ms.date: 04/28/2020
targetos: Windows
description: "Learn more about: WheaHwErrorReportSetSectionNameDeviceDriver"
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntddk.h
api_name:
 - WheaHwErrorReportSetSectionNameDeviceDriver
f1_keywords:
 - WheaHwErrorReportSetSectionNameDeviceDriver
 - ntddk/WheaHwErrorReportSetSectionNameDeviceDriver
dev_langs:
 - c++
---

## -description

This is a helper function for updating the FRUText field of the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structure.

## -parameters

### -param BufferSet

Pointer to the buffer set received from [**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md).

### -param NameLength

Length of the supplied string.

### -param Name

Pointer to a string with which to populate the FRUText section.

## -returns

Return STATUS_SUCCESS or an error code.

## -remarks

Sections in a Common Platform Error Record (CPER) have Field Replaceable Unit (FRU) text, or *FRUText*. For details on CPER, see [Error Records](/windows-hardware/drivers/whea/error-records).

First call [**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md).

Then call this function with the buffer set from [**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md), along with a string and its length and it will populate the FRUText field of [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) with the string.

## -see-also
