---
UID: NC:ntddk._WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER
title: _WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER
author: windows-driver-content
description: 
tech.root:
ms.assetid: c458ecb8-45ea-4a7b-a873-2f362866d63d
ms.author: windowsdriverdev
ms.date: 3/5/2019
ms.topic: callback
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
 - UserDefined
api_location: 
 - ntddk.h
api_name: 
 - _WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# _WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER callback function

## -description

A driver's *_WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER* callback function is called when an error source is ready to receive error reports.

## -prototype

```
//Declaration

_WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER WheaErrorSourceReadyDeviceDriver; 

// Definition

VOID WheaErrorSourceReadyDeviceDriver 
(
	PVOID ErrorSourceDesc
	PVOID Context
)
{...}

```

## -parameters

### -param ErrorSourceDesc: 

A pointer to the error source descriptor.

### -param Context: 

A pointer to the context that the driver supplied when it called [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).

## -returns

Returns VOID.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER**](ns-ntddk-whea_error_source_configuration_device_driver.md) and then calling [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md).


After this routine is called, the driver can report errors by calling [**WheaReportHwErrorDeviceDriver**](nf-ntddk-wheareporthwerrordevicedriver.md). 

## -see-also
