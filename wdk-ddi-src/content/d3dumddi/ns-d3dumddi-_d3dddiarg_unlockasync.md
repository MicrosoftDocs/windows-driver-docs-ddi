---
UID: NS:d3dumddi._D3DDDIARG_UNLOCKASYNC
title: _D3DDDIARG_UNLOCKASYNC (d3dumddi.h)
description: The D3DDDIARG_UNLOCKASYNC structure describes a resource or a surface within the resource to unlock.
old-location: display\d3dddiarg_unlockasync.htm
tech.root: display
ms.assetid: 27d4a7fa-ac2a-4049-8c9f-5ac9338c70b3
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_UNLOCKASYNC structure"]
ms.keywords: D3DDDIARG_UNLOCKASYNC, D3DDDIARG_UNLOCKASYNC structure [Display Devices], UMDisplayDriver_param_Structs_1b08f2e6-73cd-4390-a9a2-54e604ca5012.xml, _D3DDDIARG_UNLOCKASYNC, d3dumddi/D3DDDIARG_UNLOCKASYNC, display.d3dddiarg_unlockasync
f1_keywords:
 - "d3dumddi/D3DDDIARG_UNLOCKASYNC"
 - "D3DDDIARG_UNLOCKASYNC"
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
- D3DDDIARG_UNLOCKASYNC
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_UNLOCKASYNC
---

# _D3DDDIARG_UNLOCKASYNC structure


## -description


The D3DDDIARG_UNLOCKASYNC structure describes a resource or a surface within the resource to unlock. 


## -struct-fields




### -field hResource

[in] A handle to the resource to be unlocked. 


### -field SubResourceIndex

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be unlocked.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_unlockasyncflags">D3DDDI_UNLOCKASYNCFLAGS</a> structure that indicates, in bit-field flags, how to unlock the resource.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockasync">UnlockAsync</a>
 

 

