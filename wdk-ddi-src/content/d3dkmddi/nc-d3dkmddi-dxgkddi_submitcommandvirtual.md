---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMANDVIRTUAL
title: DXGKDDI_SUBMITCOMMANDVIRTUAL (d3dkmddi.h)
description: DxgkDdiSubmitCommandVirtual submits a direct memory access (DMA) buffer to a context that supports virtual addressing.
ms.date: 05/22/2025
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_SUBMITCOMMANDVIRTUAL
 - d3dkmddi/DXGKDDI_SUBMITCOMMANDVIRTUAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SUBMITCOMMANDVIRTUAL
---

# DXGKDDI_SUBMITCOMMANDVIRTUAL callback function

## -description

The **DxgkDdiSubmitCommandVirtual** command submits a DMA buffer to a context that supports virtual addressing.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver (KMD) previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pSubmitCommand

A pointer to a [**DXGKARG_SUBMITCOMMANDVIRTUAL**](ns-d3dkmddi-_dxgkarg_submitcommandvirtual.md) structure that describes operation.

## -returns

| **Value** | **Description** |
|:--|:--|
| STATUS_SUCCESS | The submitted command is well-formed. |
| STATUS_INVALID_PARAMETER | The DMA or private data is determined to be malformed. In this case, the OS will put the calling device in an error state and all subsequent calls on it will fail. The **SubmissionFenceId** value passed to this call will be considered completed after all previous packets on the hardware finished and at that point the driver notion of the last completed fence ID should be updated to this value. This behavior is different from a call to[**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md), where no error is allowed to be returned due to the ability to validate the data in a prior [**DxgkDdiRender**](nc-d3dkmddi-dxgkddi_render.md)  call. |

All other return values will lead to an OS bugcheck.

## -remarks

**DxgkDdiSubmitCommandVirtual** works with virtual memory addressing, whereas [**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md) is called with physical memory. **DxgkDdiSubmitCommandVirtual** allows the driver to manage memory more flexibly.

The GPU might have previously worked with a different address space, perhaps for another process or context. The driver is responsible for making sure the correct address space is restored ahead of submitting a particular DMA buffer.

## -see-also

[**DXGKARG_SUBMITCOMMANDVIRTUAL**](ns-d3dkmddi-_dxgkarg_submitcommandvirtual.md)

[**DxgkDdiRender**](nc-d3dkmddi-dxgkddi_render.md)

[**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md)
