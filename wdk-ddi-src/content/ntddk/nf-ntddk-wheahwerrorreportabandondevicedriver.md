---
UID: NF:ntddk.WheaHwErrorReportAbandonDeviceDriver
title: WheaHwErrorReportAbandonDeviceDriver
ms.date: 04/02/2020
ms.topic: language-reference
tech.root: whea
ms.assetid: 4a176efe-7e1a-4811-b8d7-ae78933328d7
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
 - WheaHwErrorReportAbandonDeviceDriver
f1_keywords:
 - ntddk/WheaHwErrorReportAbandonDeviceDriver
dev_langs:
 - c++
---

## -description

This routine abandons the in progress error report and releases its resources.

## -parameters

### -param ErrorHandle

The handle returned by [**WheaCreateHwErrorReportDeviceDriver**](nf-ntddk-wheacreatehwerrorreportdevicedriver.md).

## -returns

Returns STATUS_SUCCESS or STATUS_INVALID_HANDLE if the handle is invalid.

## -remarks

If [**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md) fails, or the error is no longer valid, the driver can call this routine to clean up resources without submitting a report to WHEA.

## -see-also

