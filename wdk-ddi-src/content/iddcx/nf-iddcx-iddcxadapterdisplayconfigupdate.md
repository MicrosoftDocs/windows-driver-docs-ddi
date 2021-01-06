---
UID: NF:iddcx.IddCxAdapterDisplayConfigUpdate
title: IddCxAdapterDisplayConfigUpdate function
author: windows-driver-content
description: IddCxAdapterDisplayConfigUpdate updates the display configuration for the remote session.
tech.root: display
ms.date: 09/24/2020
keywords: ["IddCxAdapterDisplayConfigUpdate function"]
ms.keywords: IddCxAdapterDisplayConfigUpdate
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
ms.custom: rs6, 19H1
f1_keywords:
 - IddCxAdapterDisplayConfigUpdate
 - iddcx/IddCxAdapterDisplayConfigUpdate
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxAdapterDisplayConfigUpdate
product:
 - Windows
dev_langs:
 - c++
---

# IddCxAdapterDisplayConfigUpdate function

## -description

**IddCxAdapterDisplayConfigUpdate** updates the display configuration for the remote session.

## -parameters

### -param AdapterObject

[in] The adapter object of the remote adapter that the display configuration is specified for.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE**](ns-iddcx-idarg_in_adaptersetrenderadapter.md) structure containing input arguments to the function.

## -returns

**IddCxAdapterDisplayConfigUpdate** returns STATUS_SUCCESS upon success; otherwise, it returns an appropriate error code. See Remarks.

## -remarks

An indirect display driver (IDD) calls **IddCxAdapterDisplayConfigUpdate** when it receives a new display configuration.

The OS returns STATUS_SUCCESS if it has stored the newly specified display configuration. These changes will asynchronously reconfigure the swapchains for the monitors as requested. **IddCxAdapterDisplayConfigUpdate** will first flush any pending monitor arrivals, and process departures to ensure that the list of monitors is current.

If **IddCxAdapterDisplayConfigUpdate** determines that the supplied display configuration is not currently supported by the driver, it returns STATUS_INVALID_PARAMETER and logs the reason using WPP for debugging purposes. For example, a driver might not support a specified resolution/refresh rate, or an invalid monitor might be specified.

**IddCxAdapterDisplayConfigUpdate** returns STATUS_GRAPHICS_INDIRECT_DISPLAY_DEVICE_STOPPED if the session this configuration change is targeted to gets disconnected or if the session adapter is being stopped.

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE**](ns-iddcx-idarg_in_adaptersetrenderadapter.md)
