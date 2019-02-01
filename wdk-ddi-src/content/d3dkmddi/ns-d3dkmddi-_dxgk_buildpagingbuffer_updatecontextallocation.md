---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
title: _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION (d3dkmddi.h)
description: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION describes an operation used to update the content of a context or device allocation.
old-location: display\dxgk_buildpagingbuffer_updatecontextallocation.htm
ms.assetid: DA23251C-E901-48A0-9B58-458622DE8CF0
ms.date: 05/10/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, d3dkmddi/DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, display.dxgk_buildpagingbuffer_updatecontextallocation
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
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

A pointer to the driver-private data that was passed in the call to <a href="https://msdn.microsoft.com/708A33C2-9620-4259-845A-2F862B6F209B">DxgkCbUpdateContextAllocation</a>.


### -field DriverPrivateDataSize

The size of the driver-private data.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/708A33C2-9620-4259-845A-2F862B6F209B">DxgkCbUpdateContextAllocation</a>
 

 

