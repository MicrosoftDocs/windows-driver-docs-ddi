---
UID: NF:iddcx.IddCxAdapterDisplayConfigUpdate
title: IddCxAdapterDisplayConfigUpdate function
author: windows-driver-content
description: Called when a new display configuration is received by the driver.
tech.root: display
ms.assetid: 38d12545-6ee4-49d2-93ba-c9c1fa89c968
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: function
f1_keywords:
 - "iddcx/IddCxAdapterDisplayConfigUpdate"
ms.keywords: IddCxAdapterDisplayConfigUpdate
req.header: iddcx.h
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
 - DllExport
api_location: 
 - IddCx.dll
api_name: 
 - IddCxAdapterDisplayConfigUpdate
product: 
 - Windows
targetos: Windows
ms.custom: rs6, 19H1
---

# IddCxAdapterDisplayConfigUpdate function


## -description

Called when a new display configuration is received by the driver.

## -parameters

### -param AdapterObject

The adapter object of the remote adapter that the display configuration is specified for.

### -param pInArgs

Input arguments of function,

## -returns

If STATUS_SUCCESS is returned then the OS has stored the new display configuration specified and asynchronously the changes will reconfigure the swapchains for the monitors as requested. This call will first flush any pending monitor arrivals or departures will be process to ensure list of monitor is current. If the call determines the supplied display configuration is not currently supported by the driver it will return STATUS_INVALID_PARAMETER and the reason will be logged using WPP for debugging purposes, for example is a given resolution/refresh rate are not supported or if an invalid monitor is specified.

## -remarks

## -see-also
