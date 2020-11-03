---
UID: NC:iddcx.PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS
title: PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS
ms.date: 10/20/2020
ms.assetid: 8b5dd011-efc0-42fc-b7d4-1915c6a6c44f
tech.root: display
ms.topic: language-reference
targetos: Windows
description: PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS is a pointer to an OS callback function through which to get the physical contiguous address of a swapchain.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 20H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS
f1_keywords:
 - PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS
 - iddcx/PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS
dev_langs:
 - c++
---

## -description

**PFN_IDDCXSWAPCHAINGETPHYSICALLYCONTIGUOUSADDRESS** is a pointer to an OS callback function through which to retrieve the physical address of the specified swapchain's currently acquired surface.

## -parameters

### -param DriverGlobals

[in] Pointer to an [**IDD_DRIVER_GLOBALS**](/windows-hardware/drivers/ddi/iddcx/ns-iddcx-idd_driver_globals) structure containing system-defined per-driver data.

### -param SwapChainObject

[in] The [IDDCX_SWAPCHAIN](/windows-hardware/drivers/display/iddcx-objects) object passed to the [**EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN**](nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md) call.

### -param pSurfaceAddresss

[out] Output arguments. On success, **pSurfaceAddress** is filled with the physical address of the surface.

## -returns

If the routine succeeds it return S_OK. If the surface was not allocated in physically contiguous memory this routine will return E_NOINTERFACE.

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxSwapChainGetPhysicallyContiguousAddress**](nf-iddcx-iddcxswapchaingetphysicallycontiguousaddress.md).

## -see-also

[**IddCxSwapChainGetPhysicallyContiguousAddress**](nf-iddcx-iddcxswapchaingetphysicallycontiguousaddress.md)
