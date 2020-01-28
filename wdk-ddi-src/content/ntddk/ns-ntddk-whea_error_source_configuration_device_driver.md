---
UID: NS:ntddk._WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
title: WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
author: windows-driver-content
description: 
tech.root:
ms.assetid: c7a125f7-fc0b-4c16-b6a1-ea7f946d778b
ms.author: windowsdriverdev
ms.date: 03/05/2019
f1_keywords:
 - "ntddk/WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER"
ms.keywords: WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, *PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, 
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, *PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddk.h
api_name: 
 - WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER structure

## -description


## -struct-fields

### -field Initialize

A pointer to the driver's [*WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md) event callback function.

### -field Uninitialize

A pointer to the driver's [*WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_uninitialize_device_driver.md) event callback function.

### -field Ready

A pointer to the driver's [*WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_ready_device_driver.md) event callback function.

## -remarks

The WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER structure is used as input to the [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md) function.

## -see-also
