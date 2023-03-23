---
UID: NS:d3dkmddi._DXGKARG_VALIDATESUBMITCOMMAND
title: DXGKARG_VALIDATESUBMITCOMMAND (d3dkmddi.h)
description: Learn more about the DXGKARG_VALIDATESUBMITCOMMAND structure.
ms.date: 03/23/2023
keywords: ["DXGKARG_VALIDATESUBMITCOMMAND structure"]
ms.keywords: _DXGKARG_VALIDATESUBMITCOMMAND, DXGKARG_VALIDATESUBMITCOMMAND, *INOUT_PDXGKARG_VALIDATESUBMITCOMMAND
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_VALIDATESUBMITCOMMAND
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARG_VALIDATESUBMITCOMMAND
 - d3dkmddi/_DXGKARG_VALIDATESUBMITCOMMAND
 - DXGKARG_VALIDATESUBMITCOMMAND
 - d3dkmddi/DXGKARG_VALIDATESUBMITCOMMAND
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_VALIDATESUBMITCOMMAND
 - DXGKARG_VALIDATESUBMITCOMMAND
dev_langs:
 - c++
---

# DXGKARG_VALIDATESUBMITCOMMAND structure

## -description

The **DXGKARG_VALIDATESUBMITCOMMAND** structure contains arguments used in the call to [**DXGKDDI_VALIDATESUBMITCOMMAND**](nc-d3dkmddi-dxgkddi_validatesubmitcommand.md).

## -struct-fields

### -field Commands

[in] The GPU virtual address of the start of the command buffer.

### -field CommandLength

[in] Length of the command buffer, in bytes.

### -field Flags

[in] A [**DXGK_VALIDATESUBMITCOMMANDFLAGS**](ns-d3dkmddi-_dxgk_validatesubmitcommandflags.md) value with flags needed to validate the submit command.

### -field ContextCount

[in] Number of valid handles in the **Context** array.

### -field Context

[in] Array of handles to the contexts associated with **Commands**. The handle type is determined as follows.

* **Context** is an array of driver context handles when **Flags.HardwareQueueSubmission** is 0.
* **Context** is an array of driver hardware queue handles when **Flags.HardwareQueueSubmission** is 1.

### -field pPrivateDriverData

[in/out,optional] Pointer to the private data that was passed to [**D3DKMTSubmitCommand**](../d3dkmthk/nf-d3dkmthk-d3dkmtsubmitcommand.md). This a copy of the buffer and the pointer is a kernel-mode pointer. See Remarks.

### -field PrivateDriverDataSize

[in] The total size in bytes of the private data buffer.

### -field UmdPrivateDataSize

[in] Number of bytes of the private data buffer passed from user mode. See Remarks.

### -field HwQueueProgressFenceId

[in] Identifier that represents the hardware queue progress fence. The driver should use this identifier to ensure that the command buffer has not previously been executed by the GPU when **Flags.HardwareQueueSubmission** is set.

## -remarks

The portion of **pPrivateDriverData**'s buffer that is not passed from user mode is uninitialized. The kernel-mode driver can use this portion to store its own data, which can be consumed in [**DxgkDdiSubmitCommandVirtual**](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md).

## -see-also

[**D3DKMTSubmitCommand**](../d3dkmthk/nf-d3dkmthk-d3dkmtsubmitcommand.md)

[**DXGKDDI_VALIDATESUBMITCOMMAND**](nc-d3dkmddi-dxgkddi_validatesubmitcommand.md).
