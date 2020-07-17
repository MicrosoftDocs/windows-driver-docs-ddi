---
UID: NF:iddcx.IddCxAdapterSetRenderAdapter
title: IddCxAdapterSetRenderAdapter function
author: windows-driver-content
description: TBD
tech.root: display
ms.assetid: 98694b19-628c-4e3e-959f-49445fa232c2
ms.author: windowsdriverdev
ms.date: 08/19/2019
keywords: ["IddCxAdapterSetRenderAdapter function"]
f1_keywords:
 - "iddcx/IddCxAdapterSetRenderAdapter"
 - "IddCxAdapterSetRenderAdapter"
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
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# IddCxAdapterSetRenderAdapter function

## -description

An OS callback function that a driver can call to set the preferred render adapter used to render the swapchains for the specified adapter.

## -parameters

### -param AdapterObject

Adapter object of the adapter for which the rendering adapter preference is being set.

### -param pInArgs

Input arguments for the function.

## -remarks

The driver can call **IddCxAdapterSetRenderAdapter** at anytime to change the preferred render adapter. The driver can use Dxgi enumeration to find the required render adapter LUID.  When this callback is called, the OS will attempt to re-create any existing swapchains onto the specified render adapter, and hence the user may see some visual glitches/artifacts. It is recommended that, if possible, the driver makes this call before adding any monitors.

## -see-also

[IDARG_IN_ADAPTERSETRENDERADAPTER](ns-iddcx-idarg_in_adaptersetrenderadapter.md)
