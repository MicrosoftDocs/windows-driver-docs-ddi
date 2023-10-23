---
UID: NF:iddcx.IddCxSwapChainReleaseAndAcquireBuffer
title: IddCxSwapChainReleaseAndAcquireBuffer function (iddcx.h)
description: Learn more about the IddCxSwapChainReleaseAndAcquireBuffer function.
tech.root: display
ms.date: 09/22/2023
keywords: ["IddCxSwapChainReleaseAndAcquireBuffer function"]
ms.keywords: IddCxSwapChainReleaseAndAcquireBuffer, IddCxSwapChainReleaseAndAcquireBuffer method [Display Devices], display.iddcxswapchainreleaseandacquirebuffer, iddcx/IddCxSwapChainReleaseAndAcquireBuffer
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: IddCxStub.lib
req.dll: IddCx.dll
req.irql: _Must_inspect_result_
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxSwapChainReleaseAndAcquireBuffer
 - iddcx/IddCxSwapChainReleaseAndAcquireBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxSwapChainReleaseAndAcquireBuffer
---

# IddCxSwapChainReleaseAndAcquireBuffer function

## -description

An indirect display driver calls **IddCxSwapChainReleaseAndAcquireBuffer** to release the current buffer in the swap chain and acquire a new one. IDDs that report [FP16 support](ne-iddcx-iddcx_adapter_flags.md) must call [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md) instead.

## -parameters

### -param SwapChainObject

[in] The swap-chain object previously passed by the OS to the driver in a [**EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN**](nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md) call.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_RELEASEANDACQUIREBUFFER**](ns-iddcx-idarg_out_releaseandacquirebuffer.md) structure in which the output arguments of the function are returned.

## -returns

**IddCxSwapChainReleaseAndAcquireBuffer** returns S_OK on success; otherwise it returns an appropriate error code.

## -see-also

[**IDARG_OUT_RELEASEANDACQUIREBUFFER**](ns-iddcx-idarg_out_releaseandacquirebuffer.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
