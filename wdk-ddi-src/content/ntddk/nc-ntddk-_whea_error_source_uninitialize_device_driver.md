---
UID: NC:ntddk._WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
title: _WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER
description: 
tech.root: 
ms.assetid: ee478611-d2a5-4651-b83b-98939cb6a400
ms.author: windowsdriverdev
ms.date: 03/05/2019
keywords: ["WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER callback function"]
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
product:
 - Windows
---

# _WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER callback function


## -description

A driver's *_WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER* callback function uninitializes its error source hardware and software state.

## -parameters

### -param Context: 

A pointer to the context that the driver supplied when it called [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

## -prototype

```
//Declaration

_WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER WheaErrorSourceUninitializeDeviceDriver; 

// Definition

VOID WheaErrorSourceUninitializeDeviceDriver 
(
	PVOID Context
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) and then calling [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

## -see-also

[*WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md)

