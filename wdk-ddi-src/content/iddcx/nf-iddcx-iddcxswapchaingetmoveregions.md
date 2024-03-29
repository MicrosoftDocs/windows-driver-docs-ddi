---
UID: NF:iddcx.IddCxSwapChainGetMoveRegions
title: IddCxSwapChainGetMoveRegions function (iddcx.h)
description: An OS callback function the driver calls when it wants retrieve the move regions for the current frame.
old-location: display\iddcxswapchaingetmoveregions.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IddCxSwapChainGetMoveRegions function"]
ms.keywords: IddCxSwapChainGetMoveRegions, IddCxSwapChainGetMoveRegions method [Display Devices], display.iddcxswapchaingetmoveregions, iddcx/IddCxSwapChainGetMoveRegions
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
 - IddCxSwapChainGetMoveRegions
 - iddcx/IddCxSwapChainGetMoveRegions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxSwapChainGetMoveRegions
---

# IddCxSwapChainGetMoveRegions function


## -description

An OS callback function the driver calls when it wants retrieve the move regions for the current frame.

## -parameters

### -param SwapChainObject [in]


The swap-chain object whose current frame is being queried.

### -param pInArgs [in]


Input arguments of the function.

### -param pOutArgs [out]


Output arguments of the function.

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
