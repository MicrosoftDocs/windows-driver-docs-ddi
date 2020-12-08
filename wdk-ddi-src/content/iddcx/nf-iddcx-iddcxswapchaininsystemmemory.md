---
UID: NF:iddcx.IddCxSwapChainInSystemMemory
title: IddCxSwapChainInSystemMemory
ms.date: 10/20/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IddCxSwapChainInSystemMemory checks whether buffers for a swapchain are resident in system memory.
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
req.target-min-winverclnt: Windows 10, version 21H1
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
 - IddCxSwapChainInSystemMemory
f1_keywords:
 - IddCxSwapChainInSystemMemory
 - iddcx/IddCxSwapChainInSystemMemory
dev_langs:
 - c++
---

## -description

> [!NOTE]
> Some information on this page relates to a pre-released product which may be substantially modified before it is commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

**IddCxSwapChainInSystemMemory** checks whether buffers for a swapchain are resident in system memory.

## -parameters

### -param SwapChainObject

[in] The [IDDCX_SWAPCHAIN](/windows-hardware/drivers/display/iddcx-objects) object whose allocation is to be checked.

### -param pInSystemMemory

[out] The result of the check. Set to TRUE when buffers are resident in system memory; otherwise set to FALSE.

## -returns

**IddCxSwapChainInSystemMemory** returns S_OK on success; otherwise it returns an appropriate error code. Possible errors include **SwapChainObject** is an invalid swapchain object and **pInSystemMemory** is a null pointer.

## -remarks

The driver can call **IddCxSwapChainInSystemMemory** at any point to check if the buffers for the swapchain are resident in system memory. It is recommended that drivers call this method when a new swapchain is being assigned, but are free to call it at any point in the lifecycle of the swapchain object.

When **IddCxSwapChainInSystemMemory** returns TRUE in **pInSystemMemory**, the driver can use either [**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md) or [**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md) for releasing and acquiring buffers from the swapchain. The driver must continue to use that particular method throughout the lifetime of that particular swapchain.

When **IddCxSwapChainInSystemMemory** returns FALSE, the driver must use [**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md) to release and acquire buffers from the swapchain.

## -see-also

[**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md)

[**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md)
