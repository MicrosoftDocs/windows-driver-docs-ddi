---
UID: NC:d3dkmddi.DXGKDDI_RESETHWENGINE
tech.root: display
title: DXGKDDI_RESETHWENGINE
ms.date: 10/03/2023
targetos: Windows
description: Learn more about the DXGKDDI_RESETHWENGINE function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_RESETHWENGINE
f1_keywords:
 - DXGKDDI_RESETHWENGINE
 - d3dkmddi/DXGKDDI_RESETHWENGINE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_RESETHWENGINE
---

## -description

*Dxgkrnl* calls the display miniport driver's (KMD's) **DxgkDdiResetHwEngine** function when a GPU engine reset is required.

## -parameters

### -param hAdapter

[in] A handle to the context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pResetHwEngine

[in/out] Pointer to a [**DXGKARG_RESETHWENGINE**](ns-d3dkmddi-_dxgkarg_resumehwengine.md) structure that contains information to reset the hardware engine.

## -returns

**DxgkDdiResetHwEngine** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it should return an appropriate NTSTATUS error code.

## -remarks

A **DxgkDdiResetHwEngine** implementation should call the [**DxgkCbInvalidateHwContext**](nc-d3dkmddi-dxgkcb_invalidatehwcontext.md) callback to inform the OS of all running contexts that were affected by the GPU engine reset operation. The OS will invalidate these context devices (set them in error) and won't perform future submissions.

The engine isn't considered resumed yet after **DxgkDdiResetHwEngine** is called, so contexts that weren't invalidated aren't allowed to be submitted. The OS needs to re-enable interrupts from this engine and synchronize its state with the reset GPU engine. After that, the OS will enable interrupts and call [**DxgkDdiResumeHwEngine**](nc-d3dkmddi-dxgkddi_resumehwengine.md), which instructs the GPU engine to start scheduling all runnable contexts that weren't affected by the engine reset.

Register your implementation of this callback function in the [**DRIVER_INITIALIZATION_DATA **](../dispmprt/ns-dispmprt-_driver_initialization_data.md) structure.

## -see-also

[**DXGKARG_RESETHWENGINE**](ns-d3dkmddi-_dxgkarg_resumehwengine.md)

[**DxgkDdiResumeHwEngine**](nc-d3dkmddi-dxgkddi_resumehwengine.md)
