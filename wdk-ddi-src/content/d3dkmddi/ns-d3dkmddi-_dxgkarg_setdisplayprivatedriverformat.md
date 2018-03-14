---
UID: NS:d3dkmddi._DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
title: "_DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT"
author: windows-driver-content
description: The DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure describes how to set the private-format attribute for a video present source.
old-location: display\dxgkarg_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: a09cfc9a-26e8-4984-b5c6-7ead5aa4644e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*IN_CONST_PDXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT, DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT, DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure [Display Devices], DmStructs_adfa4bbe-5e14-4a2a-acee-6d80b408f6ac.xml, _DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT, d3dkmddi/DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT, display.dxgkarg_setdisplayprivatedriverformat"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
-	DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
---

# _DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure


## -description


The DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure describes how to set the private-format attribute for a video present source. 


## -syntax


````
typedef struct _DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  HANDLE                         PrimaryAllocation;
  UINT                           PrivateDriverFormatAttribute;
} DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT;
````


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number that identifies the video present source in a path of a video present network (VidPN) topology to change the private driver format attribute of. 


### -field PrimaryAllocation

[in] If nonzero, handle to the allocation for the current primary surface for the video present source that the <b>VidPnSourceId</b> member specifies. The display miniport driver returns this handle when its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function is called to create the primary surface. This handle is returned in the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure of the primary-surface element in the <b>pAllocationInfo</b> array member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure. This handle is a pointer to a private driver data structure that contains information about the primary allocation.

If <b>PrimaryAllocation</b> is set to zero, no primary surface is currently associated with the video present source. In this situation, the video present source is not visible. 


### -field PrivateDriverFormatAttribute

[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md">DxgkDdiSetDisplayPrivateDriverFormat</a>



 

 


