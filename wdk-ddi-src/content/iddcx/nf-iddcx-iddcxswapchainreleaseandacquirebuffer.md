---
UID: NF:iddcx.IddCxSwapChainReleaseAndAcquireBuffer
title: IddCxSwapChainReleaseAndAcquireBuffer function
author: windows-driver-content
description: An OS callback function the driver calls when it wants to release the current buffer in the swap chain and acquire a new one.
old-location: display\iddcxswapchainreleaseandacquirebuffer.htm
old-project: display
ms.assetid: f9b0cf3f-cbb6-4b44-81c1-b60ae525ec17
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IddCxSwapChainReleaseAndAcquireBuffer, IddCxSwapChainReleaseAndAcquireBuffer method [Display Devices], display.iddcxswapchainreleaseandacquirebuffer, iddcx/IddCxSwapChainReleaseAndAcquireBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "_Must_inspect_result_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IddCxSwapChainReleaseAndAcquireBuffer
product: Windows
targetos: Windows
req.typenames: 
---

# IddCxSwapChainReleaseAndAcquireBuffer function


## -description




                An OS callback function the driver calls when it wants to release the current buffer in the swap chain and acquire a new one


## -syntax


````
HRESULT IddCxSwapChainReleaseAndAcquireBuffer(
  _In_  IDDCX_SWAPCHAIN                    SwapChainObject,
  _Out_ IDARG_OUT_RELEASEANDACQUIREBUFFER* pOutArgs
);
````


## -parameters




### -param SwapChainObject [in]

The swap-chain object passed to the <a href="..\iddcx\nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md">EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</a> call.


### -param pOutArgs [out]

Output arguments of function


## -returns



(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    


