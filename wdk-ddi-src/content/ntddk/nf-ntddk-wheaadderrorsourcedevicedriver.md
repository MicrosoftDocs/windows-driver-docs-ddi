---
UID: NF:ntddk.WheaAddErrorSourceDeviceDriver
title: WheaAddErrorSourceDeviceDriver function
author: windows-driver-content
description: A device driver calls WheaAddErrorSourceDeviceDriver to add an error source.
tech.root:
ms.assetid: 7a3a1b3d-dc79-4bcf-ba1f-ccce6c685cbe
ms.author: windowsdriverdev
ms.date: 3/5/2019
ms.topic: function
f1_keywords:
 - "ntddk/WheaAddErrorSourceDeviceDriver"
ms.keywords: WheaAddErrorSourceDeviceDriver
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
- 
api_location:
- ntddk.h
api_name: 
- WheaAddErrorSourceDeviceDriver
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# WheaAddErrorSourceDeviceDriver function


## -description

A device driver calls **WheaAddErrorSourceDeviceDriver** to add an error source.

## -parameters

### -param Context

Pointer to a caller-allocated context.  WHEA provides the context as a parameter to driver-supplied callback routines. 

### -param Configuration

Pointer to a structure of type [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) that contains a set of driver-supplied callback routines.

### -param NumRecordsToPreallocate

A value of type ULONG that specifies the number of records to preallocate. See Remarks for more information.

### -param MaxRawDataLength

Specifies the maximum size in bytes of the hardware error data the driver will report.


## -returns
This function method returns STATUS_SUCCESS or an appropriate error code.
## -remarks

WHEA can preallocate memory for errors that will be reported at high IRQL (i.e. in the context of a device interrupt).  For error sources reported at PASSIVE_LEVEL, preallocation is not required but if the device driver reports errors for its error source at DISPATCH_LEVEL or higher, error records must be preallocated.

## -see-also

[**WheaRemoveErrorSourceDeviceDriver**](nf-ntddk-whearemoveerrorsourcedevicedriver.md)

[**WheaReportHwErrorDeviceDriver**](nf-ntddk-wheareporthwerrordevicedriver.md)
