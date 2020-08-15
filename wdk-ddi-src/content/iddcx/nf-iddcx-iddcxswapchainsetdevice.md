---
UID: NF:iddcx.IddCxSwapChainSetDevice
title: IddCxSwapChainSetDevice function (iddcx.h)
description: An OS callback function the driver calls within its SetSwapChain routine to setup the swap-chain with a particular DXGI device.
old-location: display\iddcxswapchainsetdevice.htm
tech.root: display
ms.assetid: f1e96d8a-910e-4808-b9a3-e8c530158872
ms.date: 05/10/2018
keywords: ["IddCxSwapChainSetDevice function"]
ms.keywords: IddCxSwapChainSetDevice, IddCxSwapChainSetDevice method [Display Devices], display.iddcxswapchainsetdevice, iddcx/IddCxSwapChainSetDevice
f1_keywords:
 - "iddcx/IddCxSwapChainSetDevice"
 - "IddCxSwapChainSetDevice"
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
- IddCxSwapChainSetDevice
targetos: Windows
req.typenames: 
---

# IddCxSwapChainSetDevice function


## -description


An OS callback function the driver calls within its SetSwapChain routine to setup the swap-chain with a particular DXGI device.


## -parameters




### -param SwapChainObject 
[in]
The swap-chain object that will be setup with a particular DXGI device.


### -param pInArgs 
[in]
Input arguments to the function


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    



