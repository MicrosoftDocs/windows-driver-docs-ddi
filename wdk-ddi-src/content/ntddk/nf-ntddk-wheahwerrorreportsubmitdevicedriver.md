---
UID: NF:ntddk.WheaHwErrorReportSubmitDeviceDriver
title: WheaHwErrorReportSubmitDeviceDriver
ms.date: 04/02/2020
ms.topic: language-reference
targetos: Windows
tech.root: whea
ms.assetid: cef88e58-17d5-47eb-b8e7-5a73aa390da5
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
 - WheaHwErrorReportSubmitDeviceDriver
f1_keywords:
 - ntddk/WheaHwErrorReportSubmitDeviceDriver
 - ""
dev_langs:
 - c++
---

## -description

This routine submits an in progress error report to WHEA to be reported as a hardware error.

## -parameters

### -param ErrorHandle

The handle returned by [**WheaCreateHwErrorReportDeviceDriver**](nf-ntddk-wheacreatehwerrorreportdevicedriver.md).

## -returns

Returns STATUS_SUCCESS or one of the following:

* STATUS_INVALID_HANDLE: Invalid error handle
* STATUS_DEVICE_REMOVED: Error source has been removed
* STATUS_BUFFER_TOO_SMALL: Packet contains no sections
* STATUS_INSUFFICIENT_RESOURCES: Insufficient space for log data

Otherwise, this routine returns the status returned by [**WheaReportHwError**](nf-ntddk-wheareporthwerror.md).

## -remarks

Before calling this routine, the driver should add all desired sections by calling [**WheaAddHwErrorReportSectionDeviceDriver**](nf-ntddk-wheaaddhwerrorreportsectiondevicedriver.md).

After calling this routine, buffers in the buffer sets are no longer available for use, and the handle is invalid.

If an error has occurred, or the error is no longer valid, the driver can clean up without a report being submitted to WHEA by calling [**WheaHwErrorReportAbandonDeviceDriver**](nf-ntddk-wheahwerrorreportabandondevicedriver.md).

For more info, see [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10).

## -see-also

