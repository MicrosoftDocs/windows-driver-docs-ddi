---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMANDVIRTUAL
title: DXGKDDI_SUBMITCOMMANDVIRTUAL (d3dkmddi.h)
description: DxgkDdiSubmitCommandVirtual is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing.
old-location: display\dxgkddisubmitcommandvirtual.htm
ms.assetid: 7A55FB51-BDC2-4215-895E-3250579BEAF0
ms.date: 05/10/2018
keywords: ["DXGKDDI_SUBMITCOMMANDVIRTUAL callback function"]
ms.keywords: DXGKDDI_SUBMITCOMMANDVIRTUAL, DXGKDDI_SUBMITCOMMANDVIRTUAL callback, DxgkDdiSubmitCommandVirtual, DxgkDdiSubmitCommandVirtual callback function [Display Devices], d3dkmddi/DxgkDdiSubmitCommandVirtual, display.dxgkddisubmitcommandvirtual
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
 - "d3dkmddi/DxgkDdiSubmitCommandVirtual"
 - "DxgkDdiSubmitCommandVirtual"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiSubmitCommandVirtual
product:
 - Windows
---

# DXGKDDI_SUBMITCOMMANDVIRTUAL callback function

## -description

<b>DxgkDdiSubmitCommandVirtual</b> is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing.



The driver is responsible for making sure the correct address space is restored ahead of submitting a particular DMA buffer.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter.

### -param pSubmitCommand

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_submitcommandvirtual">DXGKARG_SUBMITCOMMANDVIRTUAL</a> structure that describes operation.

## -returns

| **Value** | **Description** | 
|:--|:--|
| STATUS_SUCCESS | The submitted command is well-formed. | 
| STATUS_INVALID_PARAMETER | The DMA or private data is determined to be malformed. In this case, the OS will put the calling device in an error state and all subsequent calls on it will fail. The *SubmissionFenceId* value passed to this call will be considered completed after all previous packets on the hardware finished and at that point the driver notion of the last completed fence ID should be updated to this value. <br/>**Note:** This behavior is different from [DxgkDdiSubmitCommand](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand)  call where no error is allowed to be returned due to the ability to validate the data in a prior [DxgkDdiRender](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render)  call. |


All other return values will lead to the OS <i>bugcheck</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_submitcommandvirtual">DXGKARG_SUBMITCOMMANDVIRTUAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a>

