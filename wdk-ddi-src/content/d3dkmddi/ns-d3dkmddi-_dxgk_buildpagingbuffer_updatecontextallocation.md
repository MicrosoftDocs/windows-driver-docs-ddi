---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
title: "_DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION describes an operation used to update the content of a context or device allocation.
old-location: display\dxgk_buildpagingbuffer_updatecontextallocation.htm
old-project: display
ms.assetid: DA23251C-E901-48A0-9B58-458622DE8CF0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, d3dkmddi/DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION, display.dxgk_buildpagingbuffer_updatecontextallocation
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
product: Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION
---

# _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION</b> describes an operation used to update the content of a context or device allocation.


## -syntax


````
typedef struct _DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION {
  D3DGPU_VIRTUAL_ADDRESS ContextAllocation;
  UINT64                 ContextAllocationSize;
  PVOID                  pDriverPrivateData;
  UINT                   DriverPrivateDataSize;
} DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION;
````


## -struct-fields




### -field ContextAllocation

A GPU virtual address in the paging process scratch area for the context allocation being updated.


### -field ContextAllocationSize

The size of the context allocation.


### -field pDriverPrivateData

A pointer to the driver-private data that was passed in the call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_updatecontextallocation.md">DxgkCbUpdateContextAllocation</a>.


### -field DriverPrivateDataSize

The size of the driver-private data.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_updatecontextallocation.md">DxgkCbUpdateContextAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

