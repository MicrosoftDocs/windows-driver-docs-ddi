---
UID: NF:iddcx.IddCxSwapChainGetMoveRegions
title: IddCxSwapChainGetMoveRegions function
author: windows-driver-content
description: n OS callback function the driver calls when it wants retrieve the move regions for the current frame.
old-location: display\iddcxswapchaingetmoveregions.htm
old-project: display
ms.assetid: ae8257a6-4d4c-446e-b144-1adfe0a28e50
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IddCxSwapChainGetMoveRegions method [Display Devices], iddcx/IddCxSwapChainGetMoveRegions, IddCxSwapChainGetMoveRegions, display.iddcxswapchaingetmoveregions
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
-	IddCxSwapChainGetMoveRegions
product: Windows
targetos: Windows
req.typenames: 
---

# IddCxSwapChainGetMoveRegions function


## -description




                n OS callback function the driver calls when it wants retrieve the move regions for the current frame


## -syntax


````
HRESULT IddCxSwapChainGetMoveRegions(
  _In_        IDDCX_SWAPCHAIN           SwapChainObject,
  _In_  const IDARG_IN_GETMOVEREGIONS*  pInArgs,
  _Out_       IDARG_OUT_GETMOVEREGIONS* pOutArgs
);
````


## -parameters




### -param SwapChainObject [in]

The swap-chain object whose current frame is being queried.


### -param pInArgs [in]

Input arguments of the function


### -param pOutArgs [out]

Output arguments of the function


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



