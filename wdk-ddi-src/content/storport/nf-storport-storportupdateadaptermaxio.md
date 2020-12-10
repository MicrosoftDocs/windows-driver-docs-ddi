---
UID: NF:storport.StorPortUpdateAdapterMaxIO
title: StorPortUpdateAdapterMaxIO function (storport.h)
description: This function can be called by a miniport to update the maximum IO's supported by an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine callback and has effect only during adapter initialization.
old-location: storage\storportupdateadaptermaxio.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortUpdateAdapterMaxIO function"]
ms.keywords: StorPortUpdateAdapterMaxIO, StorPortUpdateAdapterMaxIO function [Storage Devices], storage.storportupdateadaptermaxio, storport/StorPortUpdateAdapterMaxIO
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortUpdateAdapterMaxIO
 - storport/StorPortUpdateAdapterMaxIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortUpdateAdapterMaxIO
---

# StorPortUpdateAdapterMaxIO function

## -description

**StorPortUpdateAdapterMaxIO** can be called by a miniport to update the maximum IOs supported by an adapter.

## -parameters

### -param HwDeviceExtension

A pointer to miniport's device extension.

### -param MaxIoCount

Maximum IO's supported by the adapter.

## -returns

This function returns of the following values.

| Value | Description |
| ----- | ----------- |
| STOR_STATUS_SUCCESS | The telemetry event was successfully logged. |
| STOR_STATUS_NOT_IMPLEMENTED | The function was called on an OS version that does not support it. |
| STOR_STATUS_INVALID_PARAMETER | There is an invalid parameter. |
| STOR_STATUS_INVALID_DEVICE_REQUEST | The function was called outside of [**HwInitialize**](nc-storport-hw_initialize.md)/[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md). |

## -remarks

**StorPortUpdateAdapterMaxIO** is valid during a [**HwInitialize**](nc-storport-hw_initialize.md)/[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md) callback and has effect only during adapter initialization.

## -see-also

[**HwInitialize**](nc-storport-hw_initialize.md)

[**HwPassiveInitRoutine**](nc-storport-hw_passive_initialize_routine.md)
