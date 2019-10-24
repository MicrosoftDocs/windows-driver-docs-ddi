---
UID: NS:d3dumddi._D3DDDIARG_RENAME
title: _D3DDDIARG_RENAME (d3dumddi.h)
description: The D3DDDIARG_RENAME structure describes a resource or a surface within the resource to rename with a new allocation.
old-location: display\d3dddiarg_rename.htm
tech.root: display
ms.assetid: 3ecddaf4-bce7-4ea0-b53d-e4872fa21f81
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_RENAME, D3DDDIARG_RENAME structure [Display Devices], UMDisplayDriver_param_Structs_5acf671e-94e3-4752-89c1-b3c9e33cba7a.xml, _D3DDDIARG_RENAME, d3dumddi/D3DDDIARG_RENAME, display.d3dddiarg_rename
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_RENAME"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_RENAME
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_RENAME
---

# _D3DDDIARG_RENAME structure


## -description


The D3DDDIARG_RENAME structure describes a resource or a surface within the resource to rename with a new allocation. 


## -struct-fields




### -field hResource

[in] A handle to the resource to be renamed. 


### -field SubResourceIndex

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be renamed.


### -field hCookie

[in] A handle that represents the renamed surface instance that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function previously returned. 


### -field GpuVirtualAddress

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a>
 

 

