---
UID: NC:iddcx.PFN_IDDCXADAPTERSETRENDERADAPTER
title: PFN_IDDCXADAPTERSETRENDERADAPTER
description: PFN_IDDCXADAPTERSETRENDERADAPTER is a pointer to a system-implemented function that sets the preferred render adapter on which to render the swapchains for the specified adapter.
tech.root: display
ms.assetid: 0a4cd4b6-a6a2-4f23-9775-bddab232fded
ms.author: windowsdriverdev
ms.date: 09/28/2020
keywords: ["PFN_IDDCXADAPTERSETRENDERADAPTER callback pointer"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - PFN_IDDCXADAPTERSETRENDERADAPTER
 - iddcx/PFN_IDDCXADAPTERSETRENDERADAPTER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXADAPTERSETRENDERADAPTER
product:
 - Windows
dev_langs:
 - c++
---

# PFN_IDDCXADAPTERSETRENDERADAPTER callback function

## -description

**PFN_IDDCXADAPTERSETRENDERADAPTER** is a pointer to a system-implemented function that sets the preferred render adapter on which to render the swapchains for the specified adapter.

## -parameters

### -param DriverGlobals

[in] Pointer to an [**IDD_DRIVER_GLOBALS**](/windows-hardware/drivers/ddi/iddcx/ns-iddcx-idd_driver_globals) structure containing system-defined per-driver data.

### -param AdapterObject

[in] The adapter object of the adapter for which the rendering adapter preference is being set.

### -param pInArgs

[in] Input arguments.

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxAdapterSetRenderAdapter**](nf-iddcx-iddcxadaptersetrenderadapter.md).

## -see-also

[**IddCxAdapterSetRenderAdapter**](nf-iddcx-iddcxadaptersetrenderadapter.md)
