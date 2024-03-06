---
UID: NC:ntddk._WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
title: WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
description: The WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER callback function uninitializes a driver's error source hardware and software state.
tech.root: whea
ms.date: 01/19/2023
keywords: ["WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER callback function"]
req.header: ntddk.h
req.include-header: Ntddk.h
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
f1_keywords:
 - _WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
 - ntddk/_WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
---

## -description

The *WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER* callback function uninitializes a driver's error source hardware and software state.

## -parameters

### -param Context

A pointer to the context that the driver supplied when it called [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) and then calling [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

## -see-also

[*WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md)
