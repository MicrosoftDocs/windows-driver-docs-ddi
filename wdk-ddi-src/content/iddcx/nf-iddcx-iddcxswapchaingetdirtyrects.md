---
UID: NF:iddcx.IddCxSwapChainGetDirtyRects
title: IddCxSwapChainGetDirtyRects function
description: An OS callback function the driver calls when it wants retrieve the dirty rects for the current frame.
old-location: display\iddcxswapchaingetdirtyrects.htm
tech.root: display
ms.assetid: 4ffe3c46-f729-4088-b69e-f39bc00f40a6
ms.date: 05/10/2018
ms.keywords: IddCxSwapChainGetDirtyRects, IddCxSwapChainGetDirtyRects method [Display Devices], display.iddcxswapchaingetdirtyrects, iddcx/IddCxSwapChainGetDirtyRects
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
req.lib: IddCxStub.lib 
req.dll: IddCx.dll 
req.irql: "_Must_inspect_result_"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	IddCx.dll
api_name:
-	IddCxSwapChainGetDirtyRects
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxSwapChainGetDirtyRects function


## -description




                An OS callback function the driver calls when it wants retrieve the dirty rects for the current frame


## -parameters




### -param SwapChainObject [in]

The swap-chain object whose current frame is being queried.


### -param pInArgs [in]

Input arguments of the function


### -param pOutArgs [out]

Output  arguments of the function


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    



