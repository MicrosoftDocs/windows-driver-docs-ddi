---
UID: NF:iddcx.IddCxSwapChainFinishedProcessingFrame
title: IddCxSwapChainFinishedProcessingFrame function (iddcx.h)
description: An OS callback function the driver calls report all GPU command for processing this frame have been queue.
old-location: display\iddcxswapchainfinishedprocessingframe.htm
tech.root: display
ms.assetid: 46c4a592-b3d4-479d-b5db-06202b5be290
ms.date: 05/10/2018
keywords: ["IddCxSwapChainFinishedProcessingFrame function"]
ms.keywords: IddCxSwapChainFinishedProcessingFrame, IddCxSwapChainFinishedProcessingFrame method [Display Devices], display.iddcxswapchainfinishedprocessingframe, iddcx/IddCxSwapChainFinishedProcessingFrame
f1_keywords:
 - "iddcx/IddCxSwapChainFinishedProcessingFrame"
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
- IddCxSwapChainFinishedProcessingFrame
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxSwapChainFinishedProcessingFrame function


## -description




                An OS callback function the driver calls to report all GPU command for processing this frame have been queued


## -parameters




### -param SwapChainObject [in]

The swap-chain object whose current frame is being queried.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    




## -remarks



If the driver copies the buffer to a staging surface so it can lock and copy the pixel data to the CPU, then the driver should call this callback once the copy from surface to staging surface has been submitted. If the driver does not call this callback the desktop will not update. It is invalid to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iddcx/nf-iddcx-iddcxswapchainreleaseandacquirebuffer">IddCxSwapChainReleaseAndAcquireBuffer</a> before calling <b>IddCxSwapChainFinishedProcessingFrame</b>



