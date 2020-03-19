---
UID: NC:iddcx.PFN_IDDCXSWAPCHAINSETDEVICE
title: PFN_IDDCXSWAPCHAINSETDEVICE (iddcx.h)
description: An OS callback function that the driver calls within its SetSwapChain routine, to set up the swap-chain with a particular DXGI device.
ms.assetid: b1f26c55-3171-4421-9948-ebdeaea12454
ms.date: 10/19/2018
keywords: ["*PFN_IDDCXSWAPCHAINSETDEVICE callback function"]
f1_keywords:
 - "iddcx/PFN_IDDCXSWAPCHAINSETDEVICE"
req.header: iddcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- PFN_IDDCXSWAPCHAINSETDEVICE
product: 
- Windows
targetos: Windows
tech.root: display
---

# *PFN_IDDCXSWAPCHAINSETDEVICE callback function

## -description

An OS callback function that the driver calls within its SetSwapChain routine, to set up the swap-chain with a particular DXGI device.

## -prototype

```cpp
//Declaration

*PFN_IDDCXSWAPCHAINSETDEVICE *PfnIddcxswapchainsetdevice;

// Definition

HRESULT *PfnIddcxswapchainsetdevice
(
	PIDD_DRIVER_GLOBALS DriverGlobals
	IDDCX_SWAPCHAIN SwapChainObject
	CONST IDARG_IN_SWAPCHAINSETDEVICE *pInArgs
)
{...}

*PFN_IDDCXSWAPCHAINSETDEVICE


```

## -parameters

### -param DriverGlobals [in]

Contains system-defined per-driver data.

### -param SwapChainObject [in]

The swap-chain object passed to the EVT_IDD_CX_MONITOR_SET_SWAPCHAIN call.

### -param *pInArgs [in]

Input arguments to the function.

## -returns

If the routine succeeds it returns S_OK. Otherwise, it returns an appropriate error code.

## -remarks


## -see-also
