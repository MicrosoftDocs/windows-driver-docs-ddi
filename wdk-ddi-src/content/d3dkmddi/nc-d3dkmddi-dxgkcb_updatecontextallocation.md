---
UID: NC:d3dkmddi.DXGKCB_UPDATECONTEXTALLOCATION
title: DXGKCB_UPDATECONTEXTALLOCATION (d3dkmddi.h)
description: DxgkCbUpdateContextAllocation is used to update the content of a context allocation.
old-location: display\dxgkcbupdatecontextallocation.htm
ms.assetid: 708A33C2-9620-4259-845A-2F862B6F209B
ms.date: 05/10/2018
ms.keywords: DXGKCB_UPDATECONTEXTALLOCATION, DXGKCB_UPDATECONTEXTALLOCATION callback, DxgkCbUpdateContextAllocation, DxgkCbUpdateContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbUpdateContextAllocation, display.dxgkcbupdatecontextallocation
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
 - "d3dkmddi/DxgkCbUpdateContextAllocation"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkCbUpdateContextAllocation
product:
 - Windows
---

# DXGKCB_UPDATECONTEXTALLOCATION callback function

## -description

<b>DxgkCbUpdateContextAllocation</b> is used to update the content of a context allocation. The video memory manager maps the specified allocation in the paging process address space than trigger an <i>UpdateContextAllocation</i> paging operation (<i>DxgkCbUpdateContextAllocation</i>), passing the kernel mode driver the specified driver private data.

The call to <b>DxgkCbUpdateContextAllocation</b> returns when the update to the context allocation is completed.

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param pArgs

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_updatecontextallocation">DXGKARGCB_UPDATECONTEXTALLOCATION</a> structure that describes the operation.

## -returns

      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_updatecontextallocation">DXGKARGCB_UPDATECONTEXTALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_updatecontextallocation">DxgkCbUpdateContextAllocation</a>

