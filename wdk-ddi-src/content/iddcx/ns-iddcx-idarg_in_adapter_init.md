---
UID: NS:iddcx.IDARG_IN_ADAPTER_INIT
title: IDARG_IN_ADAPTER_INIT (iddcx.h)
description: The IDARG_IN_ADAPTER_INIT structure contains the information needed to initialize an adapter that will be hosted on a WDF device.
old-location: display\idarg_in_adapter_init.htm
tech.root: display
ms.assetid: 2db324c8-69b1-4497-b6a7-76047baeca19
ms.date: 09/24/2020
keywords: ["IDARG_IN_ADAPTER_INIT structure"]
ms.keywords: IDARG_IN_ADAPTER_INIT, IDARG_IN_ADAPTER_INIT structure [Display Devices], display.idarg_in_adapter_init, iddcx/IDARG_IN_ADAPTER_INIT
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDARG_IN_ADAPTER_INIT
 - iddcx/IDARG_IN_ADAPTER_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_ADAPTER_INIT
---

# IDARG_IN_ADAPTER_INIT structure

## -description

The **IDARG_IN_ADAPTER_INIT** structure contains the information needed to initialize an adapter that will be hosted on a Windows Driver Framework (WDF) device.

## -struct-fields

### -field WdfDevice

The WDF object representing the device that will be hosting this WDDM adapter object.

### -field pCaps

Pointer to an [**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md) structure containing information about the capabilities of the adapter.

### -field ObjectAttributes

Pointer to a [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes) structure containing object attributes used to initialize the WDF adapter object.

## -remarks

For more information about WDF objects, see [Introduction to Framework Objects](/windows-hardware/drivers/wdf/introduction-to-framework-objects).

## -see-also

[**IDARG_OUT_ADAPTER_INIT**](ns-iddcx-idarg_out_adapter_init.md)

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)

[**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md)

[**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes)
