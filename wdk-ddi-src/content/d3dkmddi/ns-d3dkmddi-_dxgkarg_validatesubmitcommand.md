---
UID: NS:d3dkmddi._DXGKARG_VALIDATESUBMITCOMMAND
title: _DXGKARG_VALIDATESUBMITCOMMAND (d3dkmddi.h)
description: Arguments used in the call to DXGKDDI_VALIDATESUBMITCOMMAND.
ms.assetid: c1d647f6-1b10-4a58-b3af-33e45f0a19ce
ms.date: 10/19/2018
ms.topic: struct
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmddi.h
api_name: 
-	_DXGKARG_VALIDATESUBMITCOMMAND
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _DXGKARG_VALIDATESUBMITCOMMAND structure

## -description

Arguments used in the call to [DXGKDDI_VALIDATESUBMITCOMMAND](nc-d3dkmddi-dxgkddi_validatesubmitcommand.md).

## -struct-fields

### -field Commands

GPU virtual address of the command buffer.

### -field CommandLength

Command length.

### -field Flags

**HardwareQueueSubmission** is set to TRUE when [DXGKDDI_VALIDATESUBMITCOMMAND](nc-d3dkmddi-dxgkddi_validatesubmitcommand.md) is called from [DxgkDdiSubmitCommandToHwQueue](nc-d3dkmddi-dxgkddi_submitcommandtohwqueue.md). Otherwise, it is called from [D3DKMTSubmitCommand](nc-d3dkmddi-dxgkddi_submitcommand.md).

### -field ContextCount

Number of valid handles in the Context array.

### -field Context

Array of driver context handles when **Flags.HardwareQueueSubmission** is 0. An array of driver hardware queue handles when **Flags.HardwareQueueSubmission** is 1.

### -field pPrivateDriverData

Pointer to the private data, passed to D3DKMTSubmitCommand. This a copy of the buffer and the pointer is kernel mode.

### -field PrivateDriverDataSize

The total size in bytes of the private data buffer.

### -field UmdPrivateDataSize

Portion of the private data buffer in bytes, passed from user mode.

The portion of the buffer, which is not passed from user mode, is not initialized. The kernel mode driver could use this portion to store its own data, which can be consumed in [DxgkDdiSubmitCommandVirtual](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md).

### -field HwQueueProgressFenceId
 
Valid only when **Flags.HardwareQueueSubmission** is set.

## -remarks

## -see-also
