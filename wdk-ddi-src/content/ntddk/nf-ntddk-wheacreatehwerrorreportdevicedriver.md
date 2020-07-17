---
UID: NF:ntddk.WheaCreateHwErrorReportDeviceDriver
title: WheaCreateHwErrorReportDeviceDriver
ms.date: 04/01/2020
ms.topic: language-reference
tech.root: whea
ms.assetid: b4782534-323f-4feb-86d9-b220303fcd45
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
 - WheaCreateHwErrorReportDeviceDriver
f1_keywords:
 - ntddk/WheaCreateHwErrorReportDeviceDriver
 - ""
dev_langs:
 - c++
---

## -description

This routine initializes an error report.

## -parameters

### -param ErrorSourceId

A ULONG that specifies the error source for which the packet is to be created. This is provided by WHEA to the driver's [*WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md) event callback function.

### -param DeviceObject

Pointer to a DEVICE_OBJECT corresponding to the driver, or NULL.

## -returns

This function returns a handle to the in progress error, or WHEA_ERROR_HANDLE_INVALID if the error report generation fails.

## -remarks

For more info, see [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10).

## -see-also

[**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md)
