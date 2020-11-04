---
UID: NF:iddcx.IddCxAdapterSetRenderAdapter
title: IddCxAdapterSetRenderAdapter function
description: IddCxAdapterSetRenderAdapter sets the preferred render adapter on which to render the swapchains for the specified adapter.
tech.root: display
ms.assetid: 98694b19-628c-4e3e-959f-49445fa232c2
ms.author: windowsdriverdev
ms.date: 09/24/2020
keywords: ["IddCxAdapterSetRenderAdapter function"]
ms.keywords: IddCxAdapterSetRenderAdapter
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IddCxAdapterSetRenderAdapter
 - iddcx/IddCxAdapterSetRenderAdapter
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IddCxAdapterSetRenderAdapter
product:
 - Windows
dev_langs:
 - c++
---

# IddCxAdapterSetRenderAdapter function

## -description

**IddCxAdapterSetRenderAdapter** sets the preferred render adapter on which to render the swapchains for the specified adapter.

## -parameters

### -param AdapterObject

[in] Adapter object of the adapter for which the rendering adapter preference is being set.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_ADAPTERSETRENDERADAPTER**](ns-iddcx-idarg_in_adaptersetrenderadapter.md) structure containing input arguments to the function.

## -returns

None

## -remarks

An indirect display driver (IDD) can call **IddCxAdapterSetRenderAdapter** at anytime to change the preferred render adapter. The driver can use Dxgi enumeration to find the required render adapter LUID.

The OS will use the ID driver's preferred render adapter where possible. In some cases (for example, when the preferred render adapter is PnpStopped), the OS may choose a different adapter. The OS passes the actual render adapter used for a swapchain to the driver in the [**EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN**](./nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md) callback.

**IddCxAdapterSetRenderAdapter** can be called at any time to change the render LUID. The OS will immediately try to use this new render adapter for all active monitors, re-creating any existing swapchains onto it. Users might see some visual glitches/artifacts as the OS re-configures the desktop composition. To avoid glitches, if the driver knows the render adapter to use at startup time, the driver should call **IddCxAdapterSetRenderAdapter** before adding monitors and only change it while paths are active if the user has explicitly requested it, for example via a device companion application.

**IddCxAdapterSetRenderAdapter** is supported for both console and remote ID adapters.

## -see-also

[IDARG_IN_ADAPTERSETRENDERADAPTER](ns-iddcx-idarg_in_adaptersetrenderadapter.md)