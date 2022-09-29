---
UID: NC:iddcx.PFN_IDDCXSETREALTIMEGPUPRIORITY
tech.root: display
title: PFN_IDDCXSETREALTIMEGPUPRIORITY
ms.date: 08/09/2022
targetos: Windows
description: Learn more about the PFN_IDDCXSETREALTIMEGPUPRIORITY callback.
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
 - LibDef
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXSETREALTIMEGPUPRIORITY
f1_keywords:
 - PFN_IDDCXSETREALTIMEGPUPRIORITY
 - iddcx/PFN_IDDCXSETREALTIMEGPUPRIORITY
dev_langs:
 - c++
helpviewer_keywords:
 - PFN_IDDCXSETREALTIMEGPUPRIORITY
---

## -description

**PFN_IDDCXSETREALTIMEGPUPRIORITY** is a pointer to an OS callback function through which to raise the GPU priority of a DirectX device to realtime.

## -parameters

### -param DriverGlobals [in]

Pointer to an [**IDD_DRIVER_GLOBALS**](./ns-iddcx-idd_driver_globals.md) structure containing system-defined per-driver data.

### -param SwapChainObject [in]

An [**IDDCX_SWAPCHAIN**](/windows-hardware/drivers/display/iddcx-objects) object that represents the swapchain the provided DXGI device will process.

### -param pIn [in]

Pointer to a [**IDARG_IN_SETREALTIMEGPUPRIORITY**](ns-iddcx-idarg_in_setrealtimegpupriority.md) structure with additional input arguments about the DXGI device.

## -returns

If the routine succeeds it return S_OK. Otherwise, it returns an [appropriate NTSTATUS error code](/windows-hardware/drivers/kernel/ntstatus-values) such as the following.

| Error code | Meaning |
| ---------- | ------- |
| E_INVALIDARG | An invalid swapchain object was provided. |
| E_NOTIMPL    | The GPU priority boost is not supported. See Remarks. |

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxSetRealtimeGPUPriority**](nf-iddcx-iddcxsetrealtimegpupriority.md).

Setting realtime priority is not supported on WDDM 1.*x* devices; **IddCxSetRealtimeGPUPriority** will return E_NOTIMPL for such devices.

## -see-also

[**IddCxSetRealtimeGPUPriority**](nf-iddcx-iddcxsetrealtimegpupriority.md)
