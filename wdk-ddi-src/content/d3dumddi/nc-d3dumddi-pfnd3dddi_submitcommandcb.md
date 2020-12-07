---
UID: NC:d3dumddi.PFND3DDDI_SUBMITCOMMANDCB
title: PFND3DDDI_SUBMITCOMMANDCB (d3dumddi.h)
description: pfnSubmitCommandCb is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\pfnsubmitcommandcb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SUBMITCOMMANDCB callback function"]
ms.keywords: PFND3DDDI_SUBMITCOMMANDCB, PFND3DDDI_SUBMITCOMMANDCB callback, d3dumddi/pfnSubmitCommandCb, display.pfnsubmitcommandcb, pfnSubmitCommandCb, pfnSubmitCommandCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_SUBMITCOMMANDCB
 - d3dumddi/PFND3DDDI_SUBMITCOMMANDCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnSubmitCommandCb
product:
 - Windows
---

# PFND3DDDI_SUBMITCOMMANDCB callback function


## -description

<b>pfnSubmitCommandCb</b> is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing. These contexts generate commands directly from user mode, manage their own command buffer pool and don’t make use of allocation or patch location list.

<b>pfnSubmitCommandCb</b> replaces the old <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> for such contexts and must be used in its place. Contexts that operate in legacy patch mode must continue to use the old <i>pfnRenderCb</i>.

Although the user mode driver doesn’t generate patch locations it must still generate a list of the primaries that  are being written to. The video memory manager uses the allocation list to determine which primary allocations are being referenced for write by each command buffer. This information is used to synchronize rendering to the primaries with <i>Flip</i> operations.

Some kernel mode drivers need information from their user mode driver on how to submit a particular direct memory access (DMA) buffer to their GPU. In Windows Display Driver Model (WDDM) 1.0, this information was sent by the user mode driver to the kernel mode driver through the command buffer. Since DMA buffer are built directly by the user mode driver and submitted to the GPU without modification they can’t be used to send information to the kernel driver anymore. As a result, we are adding an explicit private driver data buffer to be sent along with a submission. Note that this private driver data is unidirectional and the kernel mode driver can’t return information to the user mode driver through this buffer.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_submitcommand">D3DDDICB_SUBMITCOMMAND</a> structure that describes the operation to perform.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_submitcommand">D3DDDICB_SUBMITCOMMAND</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>
