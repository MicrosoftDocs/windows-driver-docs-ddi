---
UID: NC:iddcx.PFN_IDDCXSWAPCHAINSETDEVICE
title: PFN_IDDCXSWAPCHAINSETDEVICE (iddcx.h)
description: PFN_IDDCXSWAPCHAINSETDEVICE is a pointer to an OS callback function that sets up the swap-chain with a particular DXGI device.
ms.date: 10/19/2018
keywords: ["PFN_IDDCXSWAPCHAINSETDEVICE callback function"]
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
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
tech.root: display
f1_keywords:
 - PFN_IDDCXSWAPCHAINSETDEVICE
 - iddcx/PFN_IDDCXSWAPCHAINSETDEVICE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXSWAPCHAINSETDEVICE
product:
 - Windows
---

# PFN_IDDCXSWAPCHAINSETDEVICE callback function

## -description

**PFN_IDDCXSWAPCHAINSETDEVICE** is a pointer to an OS callback function that sets up the swap-chain with a particular DXGI device.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param SwapChainObject

[in] The swap-chain object passed to the EVT_IDD_CX_MONITOR_SET_SWAPCHAIN call.

### -param pInArgs

[in] Input arguments to the function.

## -returns

If the routine succeeds it returns S_OK. Otherwise, it returns an appropriate error code.

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call[**IddCxSwapChainSetDevice**](nf-iddcx-iddcxswapchainsetdevice.md).

## -see-also

[**IddCxSwapChainSetDevice**](nf-iddcx-iddcxswapchainsetdevice.md)
