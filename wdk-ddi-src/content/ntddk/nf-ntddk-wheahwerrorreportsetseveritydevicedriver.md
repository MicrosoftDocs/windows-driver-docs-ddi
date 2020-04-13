---
UID: NF:ntddk.WheaHwErrorReportSetSeverityDeviceDriver
title: WheaHwErrorReportSetSeverityDeviceDriver
ms.date: 04/02/2020
tech.root: whea
ms.assetid: 42bc746f-3060-4125-b1c1-967e179571e4
ms.topic: language-reference
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
 - WheaHwErrorReportSetSeverityDeviceDriver
f1_keywords:
 - ntddk/WheaHwErrorReportSetSeverityDeviceDriver
dev_langs:
 - c++
---

## -description

This routine sets the error severity of the packet and sections.

## -parameters

### -param ErrorHandle

The handle returned by [**WheaCreateHwErrorReportDeviceDriver**](nf-ntddk-wheacreatehwerrorreportdevicedriver.md).

### -param ErrorSeverity

An enumeration value from [**WHEA_ERROR_SEVERITY**](ne-ntddk-_whea_error_severity.md) representing the new severity for the error.

## -returns

Returns STATUS_SUCCESS or STATUS_INVALID_HANDLE if the handle is invalid.

## -remarks

## -see-also

