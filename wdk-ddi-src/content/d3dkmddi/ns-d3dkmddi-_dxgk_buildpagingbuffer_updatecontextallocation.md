---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
title: _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION (d3dkmddi.h)
description: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION describes an operation used to update the content of a context or device allocation.
old-location: display\dxgk_buildpagingbuffer_updatecontextallocation.htm
ms.assetid: DA23251C-E901-48A0-9B58-458622DE8CF0
ms.date: 05/10/2018
keywords: ["DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure"]
ms.keywords: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, d3dkmddi/DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, display.dxgk_buildpagingbuffer_updatecontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.typenames: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
f1_keywords:
 - _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
 - d3dkmddi/_DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
 - DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
 - d3dkmddi/DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
---

# _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure


## -description

<b>DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION</b> describes an operation used to update the content of a context or device allocation.

## -struct-fields

### -field ContextAllocation

A GPU virtual address in the paging process scratch area for the context allocation being updated.

### -field ContextAllocationSize

The size of the context allocation.

### -field pDriverPrivateData

A pointer to the driver-private data that was passed in the call to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_updatecontextallocation">DxgkCbUpdateContextAllocation</a>.

### -field DriverPrivateDataSize

The size of the driver-private data.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_updatecontextallocation">DxgkCbUpdateContextAllocation</a>