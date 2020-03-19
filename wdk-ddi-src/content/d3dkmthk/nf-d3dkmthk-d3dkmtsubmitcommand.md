---
UID: NF:d3dkmthk.D3DKMTSubmitCommand
title: D3DKMTSubmitCommand function (d3dkmthk.h)
description: D3DKMTSubmitCommand is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dkmtsubmitcommand.htm
ms.assetid: E726B4AC-F003-45B3-B467-F123DBE60D87
ms.date: 05/10/2018
keywords: ["D3DKMTSubmitCommand function"]
ms.keywords: D3DKMTSubmitCommand, D3DKMTSubmitCommand function [Display Devices], d3dkmthk/D3DKMTSubmitCommand, display.d3dkmtsubmitcommand
f1_keywords:
 - "d3dkmthk/D3DKMTSubmitCommand"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTSubmitCommand
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSubmitCommand function

## -description

<b>D3DKMTSubmitCommand</b> is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing. These contexts generate commands directly from user mode, manage their own command buffer pool and don’t make use of the allocation or patch location list.

This function replaces the old <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">Render</a> function for such contexts and must be used in its place. Contexts that operate in legacy patch mode must continue to use the old <i>Render</i> function.

Although the user mode driver doesn’t generate patch locations, it must still generate a list of primaries, which are being written to. The video memory manager uses the allocation list to determine which primary allocations are being referenced for write by each command buffer. This information is used to synchronize rendering to the primaries with <i>flip</i> operations.

Some kernel mode drivers need information from their user mode driver on how to submit a particular direct memory access (DMA) buffer to their GPU. In Windows Display Driver Model (WDDM) 1.0, this information was sent by the user mode driver to the kernel mode driver through the command buffer. Since DMA buffer are built directly by the user mode driver and submitted to the GPU without modification they can’t be used to send information to the kernel driver anymore. To enable the transfer of information between the user mode and kernel mode drivers, an explicit private driver data buffer has been added to be sent along with a submission. 

> [!NOTE]
> This private driver data is unidirectional and the kernel mode driver can’t return information to the user mode driver through this buffer.

## -parameters

### -param D3DKMT_SUBMITCOMMAND

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_submitcommand">D3DKMT_SUBMITCOMMAND</a> structure that describes the operation.

## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully created.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_submitcommand">D3DKMT_SUBMITCOMMAND</a>
 

 

