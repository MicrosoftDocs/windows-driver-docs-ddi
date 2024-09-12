---
UID: NC:d3dkmddi.DXGKCB_INVALIDATEHWCONTEXT
tech.root: display
title: DXGKCB_INVALIDATEHWCONTEXT
ms.date: 07/01/2024
targetos: Windows
description: Learn more about the DXGKCB_INVALIDATEHWCONTEXT callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_INVALIDATEHWCONTEXT
f1_keywords:
 - DXGKCB_INVALIDATEHWCONTEXT
 - d3dkmddi/DXGKCB_INVALIDATEHWCONTEXT
dev_langs:
 - c++
---

## -description

A kernel-mode graphics driver (KMD) calls **DxgkcbInvalidatehwcontext** to invalidate a hardware context.

## -parameters

### -param unnamedParam1 [in]

Pointer to a [**DXGKARGCB_INVALIDATEHWCONTEXT**](ns-d3dkmddi-_dxgkargcb_invalidatehwcontext.md) structure that contains information for *Dxgkrnl* to use to invalidate the hardware context.

## -returns

**DxgkcbInvalidatehwcontext** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

KMD calls **DxgkcbInvalidatehwcontext** to notify the system when the state and resources associated with a hardware context are no longer valid or consistent, thus requiring that the context be reset or reinitialized before it can be used again. A context needs to be invalidated in the event of a hardware engine reset operation that can be due to a variety of reasons, such as recovery from a fault or reconfiguration of the GPU resources.

*Dxgkrnl* marks the context as invalid so that it's no longer scheduled for execution on the GPU. It then initiates any necessary cleanup such as releasing resources associated with the context or resetting any state associated with the context.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_INVALIDATEHWCONTEXT**](ns-d3dkmddi-_dxgkargcb_invalidatehwcontext.md) and then call **DxgkCbInvalidateHwContext** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_INVALIDATEHWCONTEXT**](ns-d3dkmddi-_dxgkargcb_invalidatehwcontext.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
