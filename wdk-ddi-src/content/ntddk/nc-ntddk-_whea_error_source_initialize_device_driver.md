---
UID: NC:ntddk._WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER
title: _WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER
description: 
tech.root: whea
ms.date: 03/05/2019
keywords: ["WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER callback function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER
 - ntddk/_WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER
product:
 - Windows
---

# _WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER callback function


## -description

A driver's *_WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER* callback function initializes its error source hardware and software state.

## -parameters

### -param Context

A pointer to the context that the driver supplied when it called [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

### -param ErrorSourceId

A ULONG value that uniquely identifies this driver as an error source.

## -returns

This function method returns STATUS_SUCCESS or an appropriate error code.

## -prototype

```
//Declaration

_WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER WheaErrorSourceInitializeDeviceDriver; 

// Definition

NTSTATUS WheaErrorSourceInitializeDeviceDriver 
(
	PVOID Context
	ULONG ErrorSourceId
)
{...}

```

## -remarks

A driver should store the error source identifier it receives as input to this callback function for later communication with WHEA. For example, if the driver detects an error condition, it calls [**WheaReportHwErrorDeviceDriver**](nf-ntddk-wheareporthwerrordevicedriver.md), providing the error data and the driver's ErrorSourceId, to report the error to WHEA. When a driver is stopped (for example to be updated), it calls [**WheaRemoveErrorSourceDeviceDriver**](nf-ntddk-whearemoveerrorsourcedevicedriver.md) to unregister its error source identifier.

Register your implementation of this callback function by setting the appropriate member of [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) and then calling [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

For more info, see [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10).

## -see-also

[*WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_uninitialize_device_driver.md)

