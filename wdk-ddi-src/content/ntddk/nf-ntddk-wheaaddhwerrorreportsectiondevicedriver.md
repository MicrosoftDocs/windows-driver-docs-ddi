---
UID: NF:ntddk.WheaAddHwErrorReportSectionDeviceDriver
title: WheaAddHwErrorReportSectionDeviceDriver
ms.date: 04/01/2020
ms.topic: language-reference
tech.root: whea
ms.assetid: a5540ec6-87b0-4b0e-ba37-7568437a11af
targetos: Windows
description: 
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
 - 
api_location:
 - ntddk.h
api_name:
 - WheaAddHwErrorReportSectionDeviceDriver
f1_keywords:
 - ntddk/WheaAddHwErrorReportSectionDeviceDriver
dev_langs:
 - c++
---

## -description

This routine adds a new section to an error report, and hands the caller a buffer set that can be populated with information.

## -parameters

### -param ErrorHandle

A WHEA_ERROR_HANDLE obtained from [**WheaCreateHwErrorReportDeviceDriver**](nf-ntddk-wheacreatehwerrorreportdevicedriver.md) that specifies the packet that is being operated on.

### -param SectionDataLength

A ULONG that specifies the length, in bytes, of the data to be added to the section.

### -param BufferSet

A pointer to a [**WHEA_DRIVER_BUFFER_SET**](ns-ntddk-whea_driver_buffer_set.md) structure that will be populated with a set of buffers for the user to interact with.

## -returns

Returns STATUS_SUCCESS or one of the following:

* STATUS_INVALID_HANDLE: The ErrorHandle is invalid.
* STATUS_DEVICE_REMOVED: The error source has been removed.
* STATUS_INSUFFICIENT_RESOURCES: There is not enough space for the data.

## -remarks

This routine can be called up to **MaxSectionsPerReport** times as specified in the [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) structure supplied to [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

## -see-also

[**WheaCreateHwErrorReportDeviceDriver**](nf-ntddk-wheacreatehwerrorreportdevicedriver.md)