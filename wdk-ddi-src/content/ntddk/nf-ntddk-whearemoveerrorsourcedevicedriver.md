---
UID: NF:ntddk.WheaRemoveErrorSourceDeviceDriver
title: WheaRemoveErrorSourceDeviceDriver function
author: windows-driver-content
description: To remove a previously added error source, a device driver calls WheaRemoveErrorSourceDeviceDriver.
tech.root:
ms.assetid: 9b631fc8-da91-4d04-b84f-b9c40497db55
ms.author: windowsdriverdev
ms.date: 04/28/2020
keywords: ["WheaRemoveErrorSourceDeviceDriver function"]
f1_keywords:
 - "ntddk/WheaRemoveErrorSourceDeviceDriver"
 - "WheaRemoveErrorSourceDeviceDriver"
ms.keywords: WheaRemoveErrorSourceDeviceDriver
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- ntddk.h
api_name: 
- WheaRemoveErrorSourceDeviceDriver
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# WheaRemoveErrorSourceDeviceDriver function


## -description

To remove a previously added error source, a device driver calls **WheaRemoveErrorSourceDeviceDriver**.

## -parameters

### -param ErrorSourceId

The error source ID WHEA provided when it called the [*_WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md) callback. 


## -returns

This function returns STATUS_SUCCESS or an error code.

STATUS_RESOURCE_IN_USE is returned if error handles are still in use.

## -remarks

This routine must be called at PASSIVE_LEVEL as it synchronously removes the device driver's error source. 

For more info, see [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10).

## -see-also

[**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md)

[**WheaReportHwErrorDeviceDriver**](nf-ntddk-whearemoveerrorsourcedevicedriver.md)
