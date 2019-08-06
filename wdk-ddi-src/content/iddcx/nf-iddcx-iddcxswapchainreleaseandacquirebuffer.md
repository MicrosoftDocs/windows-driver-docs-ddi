---
UID: NF:iddcx.IddCxSwapChainReleaseAndAcquireBuffer
title: IddCxSwapChainReleaseAndAcquireBuffer function (iddcx.h)
description: An OS callback function the driver calls when it wants to release the current buffer in the swap chain and acquire a new one.
old-location: display\iddcxswapchainreleaseandacquirebuffer.htm
tech.root: display
ms.assetid: f9b0cf3f-cbb6-4b44-81c1-b60ae525ec17
ms.date: 05/10/2018
ms.keywords: IddCxSwapChainReleaseAndAcquireBuffer, IddCxSwapChainReleaseAndAcquireBuffer method [Display Devices], display.iddcxswapchainreleaseandacquirebuffer, iddcx/IddCxSwapChainReleaseAndAcquireBuffer
ms.topic: function
f1_keywords:
 - "iddcx/IddCxSwapChainReleaseAndAcquireBuffer"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- IddCx.dll
api_name:
- IddCxSwapChainReleaseAndAcquireBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxSwapChainReleaseAndAcquireBuffer function


## -description




                An OS callback function the driver calls when it wants to release the current buffer in the swap chain and acquire a new one


## -parameters




### -param SwapChainObject [in]

The swap-chain object passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iddcx/nc-iddcx-evt_idd_cx_monitor_assign_swapchain">EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</a> call.


### -param pOutArgs [out]

Output arguments of function


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    



