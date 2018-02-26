---
UID: NF:iddcx.IddCxSwapChainFinishedProcessingFrame
title: IddCxSwapChainFinishedProcessingFrame function
author: windows-driver-content
description: An OS callback function the driver calls report all GPU command for processing this frame have been queue.
old-location: display\iddcxswapchainfinishedprocessingframe.htm
old-project: display
ms.assetid: 46c4a592-b3d4-479d-b5db-06202b5be290
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , C, F, I, IddCxSwapChainFinishedProcessingFrame, IddCxSwapChainFinishedProcessingFrame method [Display Devices], P, S, a, c, d, display.iddcxswapchainfinishedprocessingframe, e, g, h, i, iddcx/IddCxSwapChainFinishedProcessingFrame, m, n, o, p, r, s, w, x"
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
-	IddCxSwapChainFinishedProcessingFrame
product: Windows
targetos: Windows
req.typenames: 
---

# IddCxSwapChainFinishedProcessingFrame function


## -description




                An OS callback function the driver calls report all GPU command for processing this frame have been queue


## -syntax


````
HRESULT IddCxSwapChainFinishedProcessingFrame(
  _In_ IDDCX_SWAPCHAIN SwapChainObject
);
````


## -parameters




### -param SwapChainObject [in]

The swap-chain object whose current frame is being queried.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    




## -remarks



If the driver copies the buffer to a staging surface so it can lock and copy the pixel data to the CPU, then the driver should call this callback once the copy from surface to staging surface has been submitted. If the driver does not call this callback the desktop will not update. It is invalid to call <a href="..\iddcx\nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md">IddCxSwapChainReleaseAndAcquireBuffer</a> before calling <b>IddCxSwapChainFinishedProcessingFrame</b>



