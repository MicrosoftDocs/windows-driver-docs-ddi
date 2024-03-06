---
UID: NC:d3dkmddi.DXGKDDI_RESUMEHWENGINE
tech.root: display
title: DXGKDDI_RESUMEHWENGINE (d3dkmddi.h)
description: Learn more about the DXGKDDI_RESUMEHWENGINE function.
ms.date: 10/03/2023
keywords: ["DXGKDDI_RESUMEHWENGINE callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
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
ms.custom: RS5
f1_keywords:
 - DXGKDDI_RESUMEHWENGINE
 - d3dkmddi/DXGKDDI_RESUMEHWENGINE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_RESUMEHWENGINE
dev_langs:
 - c++
---

# DXGKDDI_RESUMEHWENGINE callback function

## -description

*Dxgkrnl* calls **DxgkDdiResumeHwEngine** after a GPU engine has been successfully [reset](nc-d3dkmddi-dxgkddi_resethwengine.md) to instruct the GPU scheduler to resubmit contexts that weren't invalidated by the reset.

## -parameters

### -param hAdapter

[in] A handle to the context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pResumeHwEngine

[in/out] Pointer to a [**DXGKARG_RESUMEHWENGINE**](ns-d3dkmddi-_dxgkarg_resumehwengine.md) structure that contains information to resume the hardware engine.

## -returns

**DxgkDdiResumeHwEngine** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it should return an appropriate NTSTATUS error code. If the call fails, the OS will perform a full GPU reset.

## -remarks

The engine isn't considered resumed yet after [**DxgkDdiResetHwEngine**](nc-d3dkmddi-dxgkddi_resethwengine.md) is called, so even contexts that weren't invalidated aren't allowed to be submitted. The OS needs to re-enable interrupts from this engine and synchronize its state with the reset GPU engine. After that, the OS will enable interrupts and call **DxgkDdiResumeHwEngine**, which instructs the GPU engine to start scheduling all runnable contexts that weren't affected by the engine reset.

Register your implementation of this callback function in the [**DRIVER_INITIALIZATION_DATA **](../dispmprt/ns-dispmprt-_driver_initialization_data.md) structure.

## -see-also

[**DXGKARG_RESUMEHWENGINE**](ns-d3dkmddi-_dxgkarg_resumehwengine.md)

[**DxgkDdiResetHwEngine**](nc-d3dkmddi-dxgkddi_resethwengine.md)
