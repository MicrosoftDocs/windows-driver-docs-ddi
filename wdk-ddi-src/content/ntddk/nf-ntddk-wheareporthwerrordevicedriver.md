---
UID: NF:ntddk.WheaReportHwErrorDeviceDriver
title: WheaReportHwErrorDeviceDriver function
author: windows-driver-content
description: To report a hardware error, the driver calls the WheaReportHwErrorDeviceDriver function.
tech.root:
ms.assetid: 427af50c-a051-412f-a8d2-33fdcaca47fa
ms.author: windowsdriverdev
ms.date: 3/5/2019
ms.topic: function
f1_keywords:
 - "ntddk/WheaReportHwErrorDeviceDriver"
ms.keywords: WheaReportHwErrorDeviceDriver
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- api_location: 
- ntddk.h
api_name: 
- WheaReportHwErrorDeviceDriver
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# WheaReportHwErrorDeviceDriver function


## -description

To report a hardware error, the driver calls the **WheaReportHwErrorDeviceDriver** function. 

## -parameters

### -param ErrorSourceId

The error source ID WHEA provided when it called the [*_WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md) callback. 

### -param DeviceObject

A pointer to the device object associated with the error condition. 

### -param ErrorData

The buffer containing the driver's hardware error data.  This information is hardware-specific, and must not exceed the *MaxRawDataLength* that the driver provided to [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md)
. 

### -param ErrorDataLength

A value of type ULONG specifying the size, in bytes, of the error data. 

### -param SectionTypeGuid

Specifies what type of error data is being reported.  This may be, but is not required to be, one of the GUIDs defined in the Appendix N of the [UEFI Specification](https://uefi.org/sites/default/files/resources/UEFI%20Spec%202_6.pdf), in which case the error information matches one of the specified section types.  The caller can also create a  GUID and private section format. 

### -param ErrorSeverity

An enumeration value of type [**WHEA_ERROR_SEVERITY**](ne-ntddk-_whea_error_severity.md) specifying the severity of the error condition. 

### -param DeviceFriendlyName

An optional string up to 20 bytes in length (including NULL terminator) that describes the device associated with the error condition.  This information is copied into the resulting WHEA error record and is informational only.  The intent is to place this information in the error record so when event logs are created a consumer can easily troubleshoot device problems. 


## -returns
This function method returns STATUS_SUCCESS or an appropriate error code.
## -remarks

## -see-also

[**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md)

[**WheaRemoveErrorSourceDeviceDriver**](nf-ntddk-whearemoveerrorsourcedevicedriver.md)
