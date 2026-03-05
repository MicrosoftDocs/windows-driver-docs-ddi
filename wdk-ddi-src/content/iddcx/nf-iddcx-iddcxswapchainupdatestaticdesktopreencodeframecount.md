---
UID: NF:iddcx.IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount
title: IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount function (iddcx.h)
description: An OS callback function that overrides the StaticDesktopReencodeFrameCount value specified in the parameters passed to IddCxAdapterInitAsync on a specific swap chain.
prerelease: true
old-location: 
tech.root: display
ms.date: 02/17/2026
keywords: ["IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount function"]
ms.keywords: IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount, IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount method [Display Devices], iddcx/IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
req.target-min-winversvr: 
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
 - IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount
 - iddcx/IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount
---

# IddxCxSwapChainUpdateStaticDesktopReencodeFrameCount function

## -description

**IddCxSwapChainUpdateStaticDesktopReencodeFrameCount** overrides the StaticDesktopReencodeFrameCount value specified in the parameters passed to [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md) on a specific swap chain.

## -parameters

### -param SwapChainObject [in]

The **IDDCX_SWAPCHAIN** object previously passed to the driver in a call to [**EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN**](nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md).

### -param StaticDesktopReencodeFrameCount [in]

The new StaticDesktopReencodeFrameCount value to use with the specified swap chain.

## -returns

The method returns S_OK if the operation succeeds, otherwise an appropriate HRESULT error code.

## -remarks

Drivers must specify a StaticDesktopReencodeFrameCount in the parameters passed to **IddCxAdapterInitAsync**. A driver can now use
**IddCxSwapChainUpdateStaticDesktopReencodeFrameCount** to override this value on a specific swap chain.

In some scenarios, a driver might decide to change how many reencode frames it wants to receive. The driver can call **IddCxSwapChainUpdateStaticDesktopReencodeFrameCount** to update the number of frames received for a specific swap chain from what was set when the adapter was created. This can be used to set the value from 0 to non-zero, non-zero to zero or just a different non-zero value.

> [!NOTE]
> A reencode frame is indicated by the driver being given a single empty dirty rect alongside a frame.

> [!NOTE]
> If a swap chain for a certain monitor is unassigned and a new one assigned, the reencode count starts at the value specified in the [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md) parameters.

## -see-also

[IDDCX_ADAPTER_CAPS](ns-iddcx-iddcx_adapter_caps.md)

[IDARG_IN_ADAPTER_INIT](ns-iddcx-idarg_in_adapter_init.md)