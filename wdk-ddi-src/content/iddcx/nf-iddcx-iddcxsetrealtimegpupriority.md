---
UID: NF:iddcx.IddCxSetRealtimeGPUPriority
tech.root: display
title: IddCxSetRealtimeGPUPriority
ms.date: 08/09/2022
targetos: Windows
description: Learn more about the IddCxSetRealtimeGPUPriority function.
prerelease: false
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
req.target-min-winverclnt: Windows 10, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - iddcx.h
api_name:
 - IddCxSetRealtimeGPUPriority
f1_keywords:
 - IddCxSetRealtimeGPUPriority
 - iddcx/IddCxSetRealtimeGPUPriority
dev_langs:
 - c++
helpviewer_keywords:
 - IddCxSetRealtimeGPUPriority
---

## -description

An indirect display driver (IDD) calls **IddCxSetRealtimeGPUPriority** to raise the GPU priority of a DirectX device to realtime.

## -parameters

### -param SwapChainObject [in]

An [**IDDCX_SWAPCHAIN**](/windows-hardware/drivers/display/iddcx-objects) object that represents the swapchain the provided DXGI device will process.

### -param pIn [in]

Pointer to a [**IDARG_IN_SETREALTIMEGPUPRIORITY**](ns-iddcx-idarg_in_setrealtimegpupriority.md) structure with additional input arguments about the DXGI device.

## -returns

**IddCxSetRealtimeGPUPriority** returns STATUS_SUCCESS (S_OK) if the call succeeds. Otherwise, it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values) such as the following.

| Error code | Meaning |
| ---------- | ------- |
| E_INVALIDARG | An invalid swapchain object was provided. |
| E_NOTIMPL    | The GPU priority boost is not supported. See Remarks. |

## -remarks

An IDD can call this function to ensure GPU work for processing a frame is completed in a timely manner.

On success the GPU priority for the provided DXGI device will be raised to realtime. This means any GPU work scheduled by this device will have higher priority than any regular application can set. The OS picks the exact realtime priority level to set; the chosen level in the realtime priority band might change in future OS releases.

Setting realtime priority is not supported on WDDM 1.*x* devices; **IddCxSetRealtimeGPUPriority** will return E_NOTIMPL for such devices.

## -see-also

[**IDARG_IN_SETREALTIMEGPUPRIORITY**](ns-iddcx-idarg_in_setrealtimegpupriority.md)
