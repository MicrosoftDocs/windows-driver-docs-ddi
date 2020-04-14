---
UID: NC:iddcx.PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
title: PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
author: windows-driver-content
description: Pointer to the indirect display function IddCxAdapterDisplayConfigUpdate.
tech.root: display
ms.assetid: 8c2076ea-c798-4d19-8e1f-ffc8fea44237
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback function"]
f1_keywords:
 - "iddcx/PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
 - UserDefined
api_location: 
 - iddcx.h
api_name: 
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# *PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback function

## -description

Pointer to the indirect display function [IddCxAdapterDisplayConfigUpdate](nf-iddcx-iddcxadapterdisplayconfigupdate.md).

## -prototype

```
//Declaration

*PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE *PfnIddcxadapterdisplayconfigupdate; 

// Definition

NTSTATUS *PfnIddcxadapterdisplayconfigupdate 
(
	PIDD_DRIVER_GLOBALS DriverGlobals
	IDDCX_ADAPTER AdapterObject
	 const IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE *pInArgs
)
{...}

```

## -parameters

### -param DriverGlobals

[in] Pointer to [IDD_DRIVER_GLOBALS](ns-iddcx-idd_driver_globals.md) structure.

### -param AdapterObject

[in] The adapter object of the remote adapter that the display configuration is specified for.

### -param *pInArgs

[in] Pointer to the [IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE](ns-iddcx-idarg_in_adapterdisplayconfigupdate.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS Values error code. 

## -remarks

If STATUS_SUCCESS is returned, then the OS has stored the new display configuration specified and asynchronously the changes will reconfigure the swapchains for the monitors as requested. This call will first flush any pending monitor arrivals or departures will be process to ensure that the list of monitors is current.

If the call determines the supplied display configuration is not currently supported by the driver, it will return STATUS_INVALID_PARAMETER and the reason will be logged using WPP for debugging purposes, for example is a given resolution/refresh rate are not supported or if an invalid monitor is specified.

## -see-also
