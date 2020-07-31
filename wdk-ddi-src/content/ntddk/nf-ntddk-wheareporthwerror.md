---
UID: NF:ntddk.WheaReportHwError
title: WheaReportHwError function
author: windows-driver-content
description: Drivers should not call this wrapper function.
tech.root:
ms.assetid: c550f3ec-d88d-4c31-8bb6-06b133630881
ms.author: windowsdriverdev
ms.date: 03/06/2019
keywords: ["WheaReportHwError function"]
f1_keywords:
 - "ntddk/WheaReportHwError"
 - "WheaReportHwError"
ms.keywords: WheaReportHwError
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
- HeaderDef
api_location:
- ntddk.h
api_name: 
- WheaReportHwError
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# WheaReportHwError function


## -description

Drivers should not call this wrapper function.

After the driver's [*_WHEA_ERROR_SOURCE_READY_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_ready_device_driver.md) callback function is called, the driver can report errors by calling [**WheaReportHwErrorDeviceDriver**](nf-ntddk-wheareporthwerrordevicedriver.md).

## -parameters

### -param ErrorPacket


## -returns

## -remarks

## -see-also
