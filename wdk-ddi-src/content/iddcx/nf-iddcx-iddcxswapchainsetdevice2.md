---
UID: NF:iddcx.IddCxSwapChainSetDevice2
title: IddCxSwapChainSetDevice2
ms.date: 02/27/2026
tech.root: display
targetos: Windows
description: An OS callback function the driver calls within its SetSwapChain routine to setup the swap-chain with a particular DXGI device.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
req.target-min-winversvr: 
req.target-type: Windows
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxSwapChainSetDevice2
f1_keywords:
 - IddCxSwapChainSetDevice2
 - iddcx/IddCxSwapChainSetDevice2
dev_langs:
 - c++
---

# IddCxSwapChainSetDevice2 function

## -description

An OS callback function the driver calls within its SetSwapChain routine to setup the swap-chain with a particular DXGI device.

## -parameters

### -param SwapChainObject [in]

The **IDDCX_SWAPCHAIN** object previously passed to the driver in a call to [EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN](nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md).

### -param pInArgs [in]

A pointer to an [IDARG_IN_SWAPCHAINSETDEVICE2](ns-iddcx-idarg_in_swapchainsetdevice2.md) structure that contains the input arguments of the function.

## -returns

The method returns S_OK if the operation succeeds, otherwise an appropriate HRESULT error code.

## -remarks

A driver can call **IddCxSwapChainSetDevice2** to associate a device object used to process swapchain surface objects. The driver must set the **IDARG_IN_SWAPCHAINSETDEVICE2::Type** field and the corresponding pointer in the **IDARG_IN_SWAPCHAINSETDEVICE2::Device** union.

> [!NOTE]
> A driver is responsible for checking the adapter specified by **[IDARG_IN_SETSWAPCHAIN](ns-iddcx-idarg_in_setswapchain.md).RenderAdapterLuid** in a call to the driver's **EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN** callback supports D3D12 and, in the case D3D12 isn't available, D3D11 can still be used. Drivers can check for D3D12 support in a number of ways, one of which is to obtain an **IDXGIAdapter** object using [**EnumAdapterByLuid**](/windows/win32/api/dxgi1_4/nf-dxgi1_4-idxgifactory4-enumadapterbyluid) and then try calling **D3D12CreateDevice**.

```cpp
    ComPtr<IDXGIFactory4> pFactory;
    ComPtr<IDXGIAdapter3> pRenderAdapter;
    ComPtr<ID3D12Device> pD3d12Device;

    HRESULT Result = CreateDXGIFactory2(0, IID_PPV_ARGS(&pFactory));
    if (!FAILED(Result))
    {
        // Assume RenderAdapterLuid is obtained from IDARG_IN_SETSWAPCHAIN and passed to this routine
        LUID renderAdapterLuid = /* obtain from IDARG_IN_SETSWAPCHAIN */;
        
        Result = pFactory->EnumAdapterByLuid(renderAdapterLuid, IID_PPV_ARGS(&pRenderAdapter));
        if (!FAILED(Result))
        {
            Result = D3D12CreateDevice(pRenderAdapter.Get(), D3D_FEATURE_LEVEL_12_0, IID_PPV_ARGS(&pD3d12Device));

            if (FAILED(Result))
            {
                // No D3D12, fall back to using D3D11
            }
            else
            {
                // D3D12 can be used with this swapchain
            }
        }
    }
```

> [!NOTE]
> An IddCx 1.11 driver can still call [**IddCxSwapChainSetDevice**](nf-iddcx-iddcxswapchainsetdevice.md) to associate an IDXGIDevice object with a swapchain.

## -see-also

[**IDDCX_SWAPCHAIN_DEVICE_TYPE**](ne-iddcx-iddcx_swapchain_device_type.md)

[**IDARG_IN_SWAPCHAINSETDEVICE2**](ns-iddcx-idarg_in_swapchainsetdevice2.md)

[IddCx versions](/windows-hardware/drivers/display/iddcx-versions)
