---
UID: NF:ntddk.WheaAddErrorSourceDeviceDriver
title: WheaAddErrorSourceDeviceDriver function
author: windows-driver-content
description: A device driver calls WheaAddErrorSourceDeviceDriver to add an error source.
tech.root: whea
ms.assetid: 7a3a1b3d-dc79-4bcf-ba1f-ccce6c685cbe
ms.author: windowsdriverdev
ms.date: 04/01/2020
keywords: ["WheaAddErrorSourceDeviceDriver function"]
ms.keywords: WheaAddErrorSourceDeviceDriver
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
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
targetos: Windows
f1_keywords:
 - WheaAddErrorSourceDeviceDriver
 - ntddk/WheaAddErrorSourceDeviceDriver
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaAddErrorSourceDeviceDriver
product:
 - Windows
---

# WheaAddErrorSourceDeviceDriver function


## -description

A device driver calls **WheaAddErrorSourceDeviceDriver** to add an error source.

## -parameters

### -param Context

An optional pointer to a caller-allocated context.  WHEA provides the context as a parameter to driver-supplied callback routines. Can be NULL.

### -param Configuration

Pointer to a structure of type [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) that contains a set of driver-supplied callback routines.

### -param NumberPreallocatedErrorReports

A value of type ULONG that specifies the number of records to preallocate. See Remarks for more information.

## -returns

This function method returns STATUS_SUCCESS if the error source is added. Otherwise it can return one of the following:

* STATUS_INVALID_PARAMETER: The configuration is missing initialize and/or uninitialize callback pointers.
* STATUS_INVALID_PARAMETER_2: A configuration with an invalid version was submitted.
* STATUS_INSUFFICIENT_RESOURCES: WHEA was unable to allocate space for the error source and its records.

## -remarks

To remove an error source, the driver calls [**WheaRemoveErrorSourceDeviceDriver**](nf-ntddk-whearemoveerrorsourcedevicedriver.md).

WHEA can preallocate memory for errors that will be reported at high IRQL (i.e. in the context of a device interrupt).  For error sources reported at PASSIVE_LEVEL, preallocation is not required but if the device driver reports errors for its error source at DISPATCH_LEVEL or higher, error records must be preallocated.

For more info, see [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10).

## -see-also

[**WheaRemoveErrorSourceDeviceDriver**](nf-ntddk-whearemoveerrorsourcedevicedriver.md)

[**WheaReportHwErrorDeviceDriver**](nf-ntddk-wheareporthwerrordevicedriver.md)

[**WheaCreateHwErrorReportDeviceDriver**](nf-ntddk-wheacreatehwerrorreportdevicedriver.md)

