---
UID: NC:d3dkmddi.DXGKDDI_VALIDATESUBMITCOMMAND
title: DXGKDDI_VALIDATESUBMITCOMMAND (d3dkmddi.h)
description: Learn more about the DXGKDDI_VALIDATESUBMITCOMMAND callback function.
ms.date: 03/23/2023
keywords: ["DXGKDDI_VALIDATESUBMITCOMMAND callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_VALIDATESUBMITCOMMAND
 - d3dkmddi/DXGKDDI_VALIDATESUBMITCOMMAND
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VALIDATESUBMITCOMMAND
dev_langs:
 - c++
---

# DXGKDDI_VALIDATESUBMITCOMMAND callback function

## -description

The kernel-mode display miniport's (KMD's) **DXGKDDI_VALIDATESUBMITCOMMAND** function validates private driver data that the user-mode driver (UMD) passes in calls to [**D3DKMTSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md) or [**D3DKMTSubmitCommandToHwQueue**](../d3dkmthk/nf-d3dkmthk-d3dkmtsubmitcommandtohwqueue.md).

## -parameters

### -param hContext

[in] A handle to the miniport device context, which the KMD returned from [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md).

### -param pArgs

[in/out] Pointer to a [**DXGKARG_VALIDATESUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_validatesubmitcommand.md) structure containing information needed to validate the submit command.

## -returns

**DXGKDDI_VALIDATESUBMITCOMMAND** returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) value such as one of the following:

* STATUS_SUCCESS
* STATUS_INVALID_USER_BUFFER

## -remarks

When the KMD implements this callback, the KMD always validates private data passed in calls to:

* [**DxgkDdiSubmitCommandVirtual**](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md)
* [**DxgkDdiSubmitCommandToHwQueue**](nc-d3dkmddi-dxgkddi_submitcommandtohwqueue.md)

This callback is called only when the private driver size ([**DmaBufferPrivateDataSize**](ns-d3dkmddi-_dxgkarg_submitcommand.md)) in [**D3DKMTSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md) is not zero.

It is called once per **D3DKMTSubmitCommand** or [**D3DKMTSubmitCommandToHwQueue**](../d3dkmthk/nf-d3dkmthk-d3dkmtsubmitcommandtohwqueue.md).

The KMD should not assume that this callback is called in the context of the process that called **D3DKMTSubmitCommand**. Therefore, the UMD should not pass any user-mode pointers or handles in its private data.

This callback is called before the command is submitted to the GPU scheduler software queue for execution.

## -see-also

[**DXGKARG_VALIDATESUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_validatesubmitcommand.md)
