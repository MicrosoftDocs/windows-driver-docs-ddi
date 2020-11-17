---
UID: NF:iddcx.IddCxSwapChainGetPhysicallyContiguousAddress
title: IddCxSwapChainGetPhysicallyContiguousAddress
ms.date: 10/20/2020
ms.assetid: 129ed7f8-54b2-4153-b162-475eda6eeee4
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IddCxSwapChainGetPhysicallyContiguousAddress retrieves the physical address of the specified swapchain's currently acquired surface.
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
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxSwapChainGetPhysicallyContiguousAddress
f1_keywords:
 - IddCxSwapChainGetPhysicallyContiguousAddress
 - iddcx/IddCxSwapChainGetPhysicallyContiguousAddress
dev_langs:
 - c++
---

## -description

**IddCxSwapChainGetPhysicallyContiguousAddress** retrieves the physical address of the specified swapchain's currently acquired surface.

## -parameters

### -param SwapChainObject

[in] The [IDDCX_SWAPCHAIN](/windows-hardware/drivers/display/iddcx-objects) object used to query the physical address of the currently acquired surface.

### -param pSurfaceAddresss

[out] Pointer to a PHYSICAL_ADDRESS variable that is filled in with either the physical address of a surface or nullptr.

## -returns

**IddCxSwapChainGetPhysicallyContiguousAddress** returns S_OK on success and indicates a valid physical pointer in **pSurface**. If the initial request to allocate primaries in physically contiguous memory could not be satisfied then this method will return E_NOINTERFACE. If a surface has not been currently acquired, or if **pSurface** is nullptr then this method will return E_INVALIDARG.

## -remarks

**IddCxSwapChainGetPhysicallyContiguousAddress** looks up the currently acquired surface of the specified swapchain and first performs a wait for any pending render commands. Once the wait is successful, it retrieves the physical address of the surface if the initial request succeeded, and then performs a cache flush and invalidation on the range that contains the surface.

## -see-also

[**IDDCX_ADAPTER_FLAGS**](ne-iddcx-iddcx_adapter_flags.md)

[**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md)

[**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md)
